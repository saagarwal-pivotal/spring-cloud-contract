# Spring cloud Contracts - Provider Side
---

### Provider Side Changes


### Step 1

Create contracts directory with appropriate maven groupid folder structure



### Step 2

Create the groovy contract



### Step 3

 1. Add contract verifier dependency 
 2. Add dependency management to pull in all additional cloud depenedencies
 3. Add maven plugin for generating stubs and running contract test

```

		<dependency>
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-starter-contract-verifier</artifactId>
			<scope>test</scope>
		</dependency>
	</dependencies>

	<dependencyManagement>
		<dependencies>
			<dependency>
				<groupId>org.springframework.cloud</groupId>
				<artifactId>spring-cloud-dependencies</artifactId>
				<version>Edgware.RELEASE</version>
				<type>pom</type>
				<scope>import</scope>
			</dependency>
		</dependencies>
	</dependencyManagement>

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
			<plugin>
				<groupId>org.springframework.cloud</groupId>
				<artifactId>spring-cloud-contract-maven-plugin</artifactId>
				<version>1.2.1.RELEASE</version>
				<extensions>true</extensions>
				<configuration>
					<baseClassForTests>com.retailbank.creditcheckservice.BaseContractTest</baseClassForTests>
				</configuration>
			</plugin>
		</plugins>
	</build>
```

### Step 4

Add the base contract test class that will stub the service and set up the controller

### Step 5

Run the test
