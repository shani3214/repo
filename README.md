/*
I Written a schema where i defined two table one table related to person and other table related to Group.
In Person table 5 variable.
1. Person Name.
2. Person Age.
3. Person Weight.
4. Person Gender.
5. Person GroupId.
In Second Table 2 variable
1. GroupId.
2. GroupName.
Written Schema, Schema.fbs code converted in Schema_generated.h file 
Schema_generated.h file is encoded file then this file we use for decoding message.
In decoding message 
Defined flatbuffer, Add builder, Read builder and Finish builder.
from GroupId we get age and weight of person then we get average age and average weight of person.
"/
/* Written Schema*/
namespace GroupName;
enum Gender : byte {
    Male = 0,
    FeMale = 1
}
table GenderProperyKey (csharp_partial) {
    Key:Gender (id:0);
    Value:string (id:1);
}
table Group(csharp_partial){
    Id:int(id:0);
    GroupName:string(id:1);
}
table person (csharp_partial) {
    
    Name:string (id:0);
    Age:int (id:1);
    Weight:float(id:2);
    Gender:[GenderProperyKey](id:3);
    Groupid:[Group](id:4);
}



root_type person;
root_type Group;

/*
Encoded .h file generaed schema_generated.h
*/

  
  
  /* Decoding Message Main cpp code*/
#include <iostream>
#include "Schema_generated.h"

int main(int, char**)
{
    using namespace flatbuffers;
    FlatBufferBuilder builder;

    // prepare favorite numbers and write them to the buffer
    person PersonDetail("Ram",21,76.5, 0,1);
    person PersonDetail("Shyam",21,76.5, 0,1);
    person PersonDetail("GhanShyam",21,76.5, 0,1);
    auto inPerson{builder.CreateStruct(PersonDetail)};
    auto inData{CreateData(builder, Person_PersonDetail, inPerson.Union())};
    builder.Finish(inData);

    // output original numbers from struct used to write (just to be safe)
    std::cout << "Person Detail: "
        << +PersonDetail.Name() << ", "
        << +PersonDetail.Age() << ", "
        << +PersonDetail.Weight() <<", "
        << +PersonDetail.Gender()<< std::endl;

    // output final buffer size
    std::cout << builder.GetSize() << " B written" << std::endl;
      Group GroupDetail(1,"FightClub");
      std::vector<string>personName ;
      Group->Id=1;
  if(Group->Id==person->Groupid){
      float Averageage+=person->Age;
      personName.push_back(person->Name);
  }
  if(Group->Id==person->Groupid){
      float AverageWeight+=person->Weight;
  }
  Averageage=Averageage/sizeof(person);
  AverageWeight=AverageWeight/sizeof(person);
  std::cout<<GroupDetail.GroupName()<<", "<<Averageage<<", "<< AverageWeight;
  int size=personName.size();
  for(int i=0;i<size;i++){
      cout<<personName[i];
  }
  cout<<endl;
   
}
