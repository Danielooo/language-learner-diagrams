```mermaid
sequenceDiagram

    Controller->>Service: registerUser(user)
    Service->>Repository: findUser(user.username)
    Repository-->>Service: User/null
    alt User does not exist
        Service->>Repository: saveUser(user)
        Repository-->>Service: User
        Service-->Controller: User
    else User exists
        Service-->>Controller: Error("User already exists")
    end