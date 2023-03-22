 // Hard coded values / variables
 let hard = { 
    "RegisteredOfficeAddress":  ["G", 162,"1143470109"],
    "PlaceOfBusiness" : ["G",164,"457686347"],
    "EmailAddress" : ["E",170,"-487739423"],
    "MobileAddress" : ["T",122,"-1415936973"]
    }

//define method
def displaymethod(Input)[
    if ($Input)
    let Name = $Input.name
    let Attribute = $Input.addresses.attributes

    {
        "id": $Input.id,
        "Name": $Input.name,
        "Attributes":{
            "addressCategoryName": get-key($hard,$Name)[0],
            "addressNameCode":get-key($hard,$Name)[1],

            //Addresses
            "localityName":$Attribute.City,
            "addressPostcode" : $Attribute.Postcode,
            "addressStateCode" : $Attribute.RegionCode,
            "addressCountryCode" : $Attribute.CountryCode,
            "addressLine1" : $Attribute.Line1,
            "addressLine2" : $Attribute.Line2,

            //email
            "internetEmailAddress":$Input.attributes.Email,
            "StartDate": $Input.attributes.StartDate,
            
            //phone
            "phoneNumber": $Input.attribues.Number,
            "countryCallingCode" : $Input.attributes.CountryCallingCode,
        },
        "oidDigest": get-key($hard,$Name)[2]
    }]


// Run the method
{ 
"addresses" : displaymethod(.registeredOfficeAddresses[0]) + displaymethod(.ppobAddresses[0]) + displaymethod(.email) + displaymethod(.mobile)
}
