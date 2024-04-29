```mermaid
classDiagram
    class Exercises {
        +List<Exercise> exercises
    }
    class Exercise {
        +String question
        +Answer correctAnswer
    }
    class Answer {
        +String response
    }
    class FeedbackOnAnswer {
        +Exercise exercise
        +Answer answer
        +String feedback
    }
    class User {
        +String userRole   
        +String username
        +Security security
        +Exercises exercises
    }
    class Security {
        +String password
        +boolean twoFactorAuth
    }
    Exercises "1" -- "*" Exercise
    Exercise "1" -- "1" Answer
    FeedbackOnAnswer -- Exercise
    FeedbackOnAnswer -- Answer
    User "1" -- "1" Security
    User "1" -- "*" Exercises
