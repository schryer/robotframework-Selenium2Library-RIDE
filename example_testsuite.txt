*** Settings ***
Documentation     *Content overview*
...
...               This testsuite checks the user login and logout capabilities of the _python.org_ website.
Suite Setup       Open Browser    ${SITE URL}
Suite Teardown    Close Browser
Force Tags        python.org
Library           Selenium2Library
Resource          example_testsuite_resource_file.txt

*** Test Cases ***
Test Navigate To User Sign In Page
    [Documentation]    *Verifies navigation to the sign in page*
    [Tags]    navigation
    Navigate To User Sign In Page
    Page Should Contain    Username:
    Page Should Contain    Password:
    Page Should Contain Button    ${FORM BUTTON LOCATOR}
    Location Should Be    ${SIGN IN URL}

Test Sign In User
    [Documentation]    *Verifies that after login the user is directed to the main page*
    [Tags]    login
    Sign In User
    Page Should Contain    Your account
    Location Should Be    ${SITE URL}/

Test Sign Out User
    [Documentation]    *Verifies that after logout the user is directed to the main page*
    [Tags]    logout
    [Setup]    Get New Browser
    Sign Out User
    Page Should Contain    Sign In
    Location Should Be    ${SITE URL}/
