/******************************************************************************

                              Online C++ Compiler.
               Code, Compile, Run and Debug C++ program online.
Write your code in this editor and press "Run" button to compile and execute it.

*******************************************************************************/

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
