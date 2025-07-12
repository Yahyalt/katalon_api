# Katalon API Testing Project

## Overview
This is a **basic** Katalon Studio project for API testing, specifically designed to test user management operations (CRUD) through REST API endpoints. The project contains fundamental test cases for creating, reading, updating, and deleting user data.

⚠️ **Current Status**: This is a learning/personal project with room for significant improvements. See the [Areas for Improvement](#areas-for-improvement) section for details on what needs to be enhanced.

## Prerequisites
- **Katalon Studio** (version 8.0 or later recommended)
- **Java JDK** (version 8 or later)
- **Internet connection** for API calls
- **Git** (for version control)

## Project Structure

```
katalon_api/
├── Object Repository/          # API request definitions (basic setup)
│   ├── Add User.rs            # POST request for creating users
│   ├── Delete User.rs         # DELETE request for removing users
│   ├── Get All User.rs        # GET request for retrieving all users
│   ├── Get Specific User.rs   # GET request for retrieving specific user
│   ├── Update User.rs         # PUT request for updating users
│   └── coba.rs               # Additional test request
├── Test Cases/                # Test case definitions (happy path only)
│   └── API Test Cases/
│       ├── Add User with valid data.tc
│       ├── Delete User with valid data.tc
│       ├── Get All User with valid data.tc
│       ├── Get Specific User with valid data.tc
│       └── Update User with valid data.tc
├── Scripts/                   # Groovy scripts for test execution
│   └── API Test Cases/
├── Test Suites/              # Test suite configurations (basic)
│   ├── Valid status code.groovy
│   └── Valid status code.ts
├── Profiles/                 # Execution profiles (minimal setup)
├── settings/                 # Project settings and configurations
├── Include/                  # Additional configurations
└── readme.md                 # This documentation
```

### 🚫 **Missing Directories/Files**
- `Test Data/` - No data-driven testing support
- `Keywords/` - No custom reusable functions
- `config/` - No environment-specific configurations
- `docs/` - No API documentation or schemas
- `scripts/` - No utility or helper scripts
- `Dockerfile` - No containerization support
- `.github/workflows/` - No CI/CD automation

## Setup Instructions

### 1. Install Katalon Studio
1. Download Katalon Studio from [katalon.com](https://www.katalon.com/)
2. Install following the official installation guide
3. Launch Katalon Studio

### 2. Import the Project
1. Open Katalon Studio
2. Select **File → Open Project**
3. Navigate to the project directory (`katalon_api`)
4. Select the project file (`My First API Project.prj`)
5. Click **Open**

### 3. Configure Test Environment
1. Check the **Profiles** folder for environment configurations
2. Update API endpoints in the Object Repository if needed
3. Configure authentication if required

## Running Tests

### Individual Test Cases
1. Navigate to **Test Cases → API Test Cases**
2. Right-click on desired test case
3. Select **Run**
4. View results in the **Log Viewer**

### Test Suites
1. Navigate to **Test Suites**
2. Open **Valid status code.ts**
3. Click the **Run** button
4. Monitor execution in the **Job Progress**

### Command Line Execution
```bash
# Navigate to project directory
cd katalon_api

# Run specific test suite
katalonc -noSplash -runMode=console -projectPath="." -retry=0 -testSuiteCollectionPath="Test Suites/Valid status code" -browserType="Chrome" -apiKey="YOUR_API_KEY"
```

## Test Cases Description

**Note**: Current test cases cover only **happy path scenarios** with valid data. Missing negative testing, edge cases, and error handling.

### 1. Add User with Valid Data
- **Purpose**: Test user creation with valid input data
- **Method**: POST
- **Validation**: Status code 200/201, response body structure
- **Missing**: Invalid data testing, duplicate user scenarios, field validation

### 2. Get All Users with Valid Data
- **Purpose**: Retrieve all users from the system
- **Method**: GET
- **Validation**: Status code 200, response array structure
- **Missing**: Pagination testing, filtering, empty response scenarios

### 3. Get Specific User with Valid Data
- **Purpose**: Retrieve a specific user by ID
- **Method**: GET
- **Validation**: Status code 200, user data accuracy
- **Missing**: Invalid ID testing, non-existent user scenarios, unauthorized access

### 4. Update User with Valid Data
- **Purpose**: Update existing user information
- **Method**: PUT
- **Validation**: Status code 200, updated data verification
- **Missing**: Invalid data testing, partial updates, conflict scenarios

### 5. Delete User with Valid Data
- **Purpose**: Remove user from the system
- **Method**: DELETE
- **Validation**: Status code 200/204, deletion confirmation
- **Missing**: Non-existent user deletion, cascade deletion, authorization checks

## API Endpoints Configuration

The API requests are configured in the **Object Repository**. To modify endpoints:

1. Navigate to **Object Repository**
2. Double-click on the request file (e.g., `Add User.rs`)
3. Update the **Request URL** in the request editor
4. Modify **Headers**, **Parameters**, or **Body** as needed
5. Save changes

## Reporting

### View Test Results
1. After test execution, go to **Reports** folder
2. Open the generated HTML report
3. Review test execution details, pass/fail status, and logs

### Log Analysis
- Check **Log Viewer** for detailed execution logs
- Review **Console** for debug information
- Analyze **Screenshots** if UI validation is included

## Areas for Improvement

### 🚨 **Missing Critical Components**
- **Test Data Management**: No Test Data folder for data-driven testing
- **Custom Keywords**: No reusable API helper functions
- **Environment Configuration**: Limited environment management setup
- **CI/CD Integration**: No automated testing pipeline
- **Docker Support**: No containerization for consistent testing environments

### 📋 **Current Limitations**
- **Basic Test Coverage**: Only happy path scenarios covered
- **No Negative Testing**: Missing error handling and edge case validation
- **Hardcoded Values**: Test data likely embedded in test cases
- **No Performance Testing**: No load or stress testing capabilities
- **Limited Reporting**: Basic Katalon reports only
- **No API Schema Validation**: No response schema validation
- **Security Testing**: No authentication/authorization testing

### 🔧 **Recommended Next Steps**
1. **High Priority**:
   - Add Test Data folder with CSV/JSON files
   - Create Custom Keywords for common API operations
   - Implement proper environment configuration
   - Add negative test scenarios

2. **Medium Priority**:
   - Set up CI/CD pipeline (GitHub Actions)
   - Add Docker support
   - Implement API schema validation
   - Add performance testing

3. **Low Priority**:
   - Advanced reporting (Allure, custom templates)
   - API documentation generation
   - Security testing scenarios

## Best Practices (To Be Implemented)

1. **Environment Management**: Use different profiles for different environments (dev, staging, prod)
2. **Data Management**: Keep test data separate and use data-driven testing when possible
3. **Error Handling**: Implement proper error handling in test scripts
4. **Reporting**: Generate detailed reports after each test run
5. **Version Control**: Commit changes regularly with meaningful messages

## Common Issues & Troubleshooting

### Issue: Connection timeout
**Solution**: Check API endpoint availability and network connectivity

### Issue: Authentication errors
**Solution**: Verify API keys, tokens, or credentials in the request headers

### Issue: Test data conflicts
**Solution**: Use unique test data or implement data cleanup procedures

### Issue: Katalon Studio crashes
**Solution**: Check Java version compatibility and increase memory allocation

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request with detailed description

## Support

For issues or questions:
- Check Katalon Studio documentation
- Review test execution logs
- Consult Katalon Community forums

## License

This project is for personal use and testing purposes.

## Disclaimer

This is a **learning project** created for educational purposes. It serves as a foundation for API testing but requires significant enhancements for production use. The current implementation:

- ✅ **Works for**: Basic API testing scenarios and learning Katalon Studio
- ❌ **Not suitable for**: Production environments, enterprise testing, or complex API validation

## Contributing

This project welcomes contributions! Given the current limitations, any improvements would be valuable:

1. Fork the repository
2. Pick an improvement from the [Areas for Improvement](#areas-for-improvement) section
3. Create a feature branch
4. Make your changes
5. Test thoroughly
6. Submit a pull request with detailed description

---

**Note**: This project is in its early stages. Please review the [Areas for Improvement](#areas-for-improvement) section before using it for serious testing scenarios. API endpoints, authentication details, and test data need to be configured according to your specific requirements.
