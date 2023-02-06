  var jsonData = pm.response.json().result;

  pm.test("Status code is 200 OK", () => {
    pm.response.to.have.status(200);
    pm.response.to.have.status("OK");
});

pm.test("Verify on beneficiaryIban is empty", () => {
   for (var i=0; i < jsonData.items.length; i++) {
    pm.expect(jsonData.items[i].beneficiaryIban).not.empty; 
}
})

pm.test("Verify on sanctionTypeId equal 1", () => {
   for (var i=0; i < jsonData.items.length; i++) {
    pm.expect(jsonData.items[i].sanctionTypeId).is.equal(1); 
}
})

pm.test("Verfiy on countryCode is empty", () => {
   for (var i=0; i < jsonData.items.length; i++) {
    pm.expect(jsonData.items[i].countryCode).is.empty; 
}
})


pm.test("Verfiy on makerName is not empty", () => {
   for (var i=0; i < jsonData.items.length; i++) {
    pm.expect(jsonData.items[i].makerName).not.empty; 
}
})

var jsonData = pm.response.json().result;

pm.test("Status code is 200 OK", () => {
    pm.response.to.have.status(200);
    pm.response.to.have.status("OK");
});

pm.test("Verify all caseTypeName are Remittance",()=>{
    _.each(jsonData.items,(el)=>{
        pm.expect(el.caseTypeName).to.include("Remittance")
    })
})

pm.test("Verify all proposedCaseStatusName are Accepted",()=>{
    _.each(jsonData.items,(el)=>{
        pm.expect(el.proposedCaseStatusName).to.include("Accepted")
    })
})
//Bug
pm.test("Verify all CaseStatusName are Accepted",()=>{
    _.each(jsonData.items,(el)=>{
        pm.expect(el.caseStatusName).to.include("Accepted")
    })
})

pm.test("Verify all caseTypeIds", () => {
    _.each(jsonData.items, (el) => {
        pm.expect(el.caseTypeId).to.equal(1);
    })
})



pm.test("Set case id and custName and caseTypeId and acceptedBy and caseStatusId", () => {
  let array = jsonData.items.length;
    let index = Math.floor((Math.random() * array));
    
    const caseId = jsonData.items[index].id;
    const custName = jsonData.items[index].custName;
    const caseTypeId=jsonData.items[index].caseTypeId;
    const acceptedBy=jsonData.items[index].acceptedBy;
    
    pm.environment.set("caseId", caseId);
    pm.environment.set("custName", custName);
    pm.environment.set("caseTypeId", caseTypeId);
    pm.environment.set("acceptedBy",acceptedBy);

});
//Bug propsed caseStatusId is Accepted in search
pm.test("Set caseStatusId",()=>{
    let array = jsonData.items.length;
    let index = Math.floor((Math.random() * array));
    const caseStatusId= jsonData.items[index].caseStatusId;
    pm.environment.set("caseStatusId",caseStatusId);
})



