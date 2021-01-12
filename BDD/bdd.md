```sql
create table User (
    id serial,
    lastName varchar(50),
    firstName varchar(50),
    trigram varchar(10),
    isTeacher boolean,
    PRIMARY KEY (id)
);

create table Type (
    id serial,
    tag varchar(50),
    PRIMARY KEY (id)
);

create table Speciality (
    id serial,
    tag varchar(50),
    PRIMARY KEY (id)
);

create table Activity (
    id serial,
    tag varchar(50),
    goal text(1000),
    dateStart char(10),
    dateEnd char(10),
    hourStart char(5),
    hourEnd char(5),
    idType integer,
    idSpeciality integer,
    PRIMARY KEY (id),
    CONSTRAINT fk_Activity_Type FOREIGN KEY (idType) REFERENCES Type (id),
    CONSTRAINT fk_Activity_Speciality FOREIGN KEY (idSpeciality) REFERENCES Speciality (id)
);

create table toParticipate (
    idUser integer,
    idActivity integer,
    PRIMARY KEY (idUser, idActivity),
    CONSTRAINT fk_toParticipate_User FOREIGN KEY (idUser) REFERENCES User (id),
    CONSTRAINT fk_toParticipate_Activity FOREIGN KEY (idActivity) REFERENCES Activity (id)
);
```
