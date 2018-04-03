# hello-word
'''
Created on Mar 26, 2018

@author: sna
'''
import unittest
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
from time import sleep
class MenuTraverse(unittest.TestCase):
    def setUp(self):
        self.driver = webdriver.Chrome ()
        
    def test_solutions(self):
        driver = self.driver
        driver.get("http://www.rovsing.dk")
        driver.maximize_window()
        driver.find_element_by_class_name('easy-cookies-policy-accept').click()
        elem = ['Products', 'Software', 'On Board and Ground Support', 'On Site Engineering Support', 'Software Verification and Validation']
        for i in elem:
            driver.find_element_by_link_text(i).click() 
            sleep(3)  
    def tearDown(self):
        sleep(5)
        self.driver.quit()
if __name__ == "__main__":
    unittest.main() 
    
