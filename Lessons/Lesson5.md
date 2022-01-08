
[Go back to list](../)

Lesson 5. Moongose introduction.

 - usage of non relational db's. no relational - flexible types, velocity. relational - strongly typed.
   hybrid db, ODM - Moongose. tables-rows vs collections-documents
 - UML diagrams. user histories. creately
    Class Name(collection name), Attributes and types
    Example: User, {_id : string, email : string, id_number : string, name : string, surname : string,
                    user_type : Enum_Rol, state : Enum_User_State, **leading_projects : Project[]**, 
                    inscriptions : Inscription[], Progress_Created : Progress[]}; 
                    Enum_Rol {student, leader, admin}, Enum_User_State {pending, autorized, non_autorized}

    password later. enumerators (drop-down like) - another color on UML - has no types

    Project, {_id : string, name : string, objectives : , budget: float, start_date : date, end_date : date
                leader : **User** , state: Enum_Project_State, fase : Enum_Project_Fase, inscriptions : 
                Inscription[], progress : Progress[]}
                Enum_Project_State {Active, Inactive}, Enum_Project_Fase {Started, Development, Finished}

    Objective, {_id : string, description : string, type : Enum_Objective_Type}
                Enum_Objective_Type { general, specific}

    Inscription {_id : string, project : Project, student : User, state : Enum_State_Ins, enter_date : date, exit_date: date}
                Enum_State_Ins { Accepted, Denied } 

    Progress {_id : string, project : Project, date : date, description : string, observations : string, owner : User} 
 - weak references. leaderName, idName. strong references - ODM. relation types - OnetoOne (user - profile),
   OnetoMany ( user - projects, projects - objectives ), ManytoMany ( images - pages ). assign enums to collections

 - Moongose. manage db. odm object document mapper (e.g. mongoDB atlas), orm - object relational mapper, review mongoDB
   Atlas
