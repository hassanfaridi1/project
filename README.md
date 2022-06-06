# project
portfolio project land registration
//SPDX-License-identifier: GPL-3.0
pragma solidity >= 0.7.0 < 0.9.0;
contract Land {
 struct Landreg {
 uint area ;
 string location ;
 string addr ;
 address owner ;
 bool verificationStatus ;
 }
 mapping(uint256 =>   newland) public newland; 
    mapping(uint256 => address) public propOwnerChange; 
        mapping(address => userreg) public userreg; 
    mapping(address => bool) public verifiedUsers; 

 Landreg[] public lands;
function createLand(uint area, string memory location, string memory addr, address owner) public
{
 Landreg memory newLand = Landreg({
 area : area ,
 location : location ,
 addr : addr ,
 owner : owner,
 verificationStatus : false
 });

 lands.push (newLand);
}
 function updateland(Landreg memory land , uint area, string memory location, string memory addr, address
owner, bool vs) private {
 land.location = location ;
 land.area = area ;
 land.owner = owner ;
 land.addr = addr ;
 land.verificationStatus = vs;
 }
}

contract User {
 struct Userreg {
 string name ;
 string documents ;
 uint age ;
 string ty ;
 string addr ;
 bool isverified ;
 }
 Userreg[] public users ;
 function createuser(string memory name , string memory documents , uint age , string memory ty, string
memory addr ) public{
 Userreg memory newReg = Userreg({
 name : name ,
 documents : documents,
 age : age ,
 ty:ty ,
 addr : addr ,
 isverified : false
 }) ;
 users.push(newReg);
 }
 function update(Userreg memory usery , string memory name , string memory documents , uint age , string
memory ty, string memory addr , bool isverified ) public {
 usery.name = name ;
 usery.documents = documents ;
 usery.age = age ;

 usery.ty = ty;
 usery.addr = addr;
 usery.isverified = isverified;
 }
}
