# cplant
cplant(Color PLANT uml) is theme for the plant UML.

![azusa-color](sample_seq.png)

```uml
@startuml
!define BLACK   #363D5D
!define RED     #F6363F
!define PINK    #F6216E
!define MAGENTA #A54FBD
!define GREEN   #37A77C
!define YELLOW  #F97A00
!define BLUE    #1E98F2
!define CYAN    #25AFCA
!define WHITE   #FEF2DC

' Base Setting
skinparam Shadowing false
skinparam BackgroundColor transparent
skinparam ComponentStyle uml2
skinparam Default {
  FontName  'Hiragino Sans'
  FontColor BLACK
  FontSize  10
  FontStyle plain
}

skinparam Sequence {
  ArrowThickness 1
  ArrowColor RED
  ActorBorderThickness 1
  LifeLineBorderColor GREEN
  ParticipantBorderThickness 0
}
skinparam Participant {
  BackgroundColor BLACK
  BorderColor BLACK
  FontColor #FFFFFF
}

skinparam Actor {
  BackgroundColor BLACK
  BorderColor BLACK
}

title <size:20>Sample Sequence</size>

actor User
participant "First Class" as A
participant "Second Class" as B
participant "Last Class" as C

User -> A: DoWork
activate A

A -> B: Create Request
activate B

B -> C: DoWork
activate C
C --> B: WorkDone
destroy C

B --> A: Request Created
deactivate B

A --> User: Done
deactivate A

@enduml

```
