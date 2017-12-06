# sample-repo


Two Models
	TestUser
		name
		email
		
	TestUserAdress
		street1
		street2
		
	TestUser
		embedsOne
			TestUserAdress
			
			
			
	1. PATCH API works fine at root level
		Eg. PATCH http://localhost:3000/api/TestUser/5a26de72c43d8226b8a38198
			{
				"email": "maddy123@mailinator.com"
			}
		
	2. PATCH API updates the whole embedded model. In the below case, street1 become null.
		Eg. PATCH http://localhost:3000/api/TestUser/5a26de72c43d8226b8a38198
			{
				"email": "maddy456@mailinator.com",
				"billingAddress" : {
					"street2": "vandello"
				}
			}
		