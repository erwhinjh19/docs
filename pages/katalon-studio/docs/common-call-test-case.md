---
title: "[Common] Call Test Case" 
sidebar: katalon_studio_docs_sidebar
permalink: katalon-studio/docs/common-call-test-case.html 
description: 
---
Description  
-------------

Call another test case and execute it separately.

Parameters  
------------

| Param | Param Type | Mandatory | Description |
| --- | --- | --- | --- |
| arg0 | TestCase | Required | Represent the called test case's path. |
| arg1 | Map<String,Object> | Required | Represent the list of parameters will be used in the called test case. |
| flowControl | FailureHandling | Optional | Specify [failure handling](https://docs.katalon.com/x/qAAM) schema to determine whether the execution should be allowed to continue or stop. |

Returns
-------

| Param Type | Description |
| --- | --- |
| Object | 
Value of called test case if any.

 |

Example 
--------

You want to verify if the returned message after logging in successfully does not match the expected message.

*   Manual view    
    ![](../../images/katalon-studio/docs/common-call-test-case/image2017-3-3 17_49_2.png)
*   Script view 
    
    ```groovy
    import static com.kms.katalon.core.checkpoint.CheckpointFactory.findCheckpoint
    import static com.kms.katalon.core.testcase.TestCaseFactory.findTestCase
    import static com.kms.katalon.core.testdata.TestDataFactory.findTestData
    import static com.kms.katalon.core.testobject.ObjectRepository.findTestObject
    import com.kms.katalon.core.checkpoint.Checkpoint as Checkpoint
    import com.kms.katalon.core.checkpoint.CheckpointFactory as CheckpointFactory
    import com.kms.katalon.core.mobile.keyword.MobileBuiltInKeywords as MobileBuiltInKeywords
    import com.kms.katalon.core.mobile.keyword.MobileBuiltInKeywords as Mobile
    import com.kms.katalon.core.model.FailureHandling as FailureHandling
    import com.kms.katalon.core.testcase.TestCase as TestCase
    import com.kms.katalon.core.testcase.TestCaseFactory as TestCaseFactory
    import com.kms.katalon.core.testdata.TestData as TestData
    import com.kms.katalon.core.testdata.TestDataFactory as TestDataFactory
    import com.kms.katalon.core.testobject.ObjectRepository as ObjectRepository
    import com.kms.katalon.core.testobject.TestObject as TestObject
    import com.kms.katalon.core.webservice.keyword.WSBuiltInKeywords as WSBuiltInKeywords
    import com.kms.katalon.core.webservice.keyword.WSBuiltInKeywords as WS
    import com.kms.katalon.core.webui.keyword.WebUiBuiltInKeywords as WebUiBuiltInKeywords
    import com.kms.katalon.core.webui.keyword.WebUiBuiltInKeywords as WebUI
    import internal.GlobalVariable as GlobalVariable
    'Use WebUI keyword'
    WebUI.callTestCase(findTestCase('DDR_NavigateToPageThenVerifyPageTitle'), ['p_Protocol' : null, 'p_DomainName' : null, 'p_Path' : null
            , 'p_WindowTitle' : null])
    
    'Use Mobile keyword'
    Mobile.callTestCase(findTestCase('DDR_NavigateToPageThenVerifyPageTitle'), ['p_Protocol' : null, 'p_DomainName' : null, 'p_Path' : null
            , 'p_WindowTitle' : null])
    
    'Use WS keyword'
    WS.callTestCase(findTestCase('DDR_NavigateToPageThenVerifyPageTitle'), ['p_Protocol' : null, 'p_DomainName' : null, 'p_Path' : null
            , 'p_WindowTitle' : null])
    
    
    
    ```