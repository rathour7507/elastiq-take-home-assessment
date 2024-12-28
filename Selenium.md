# QA Selenium Automation with Python

## Objective
Create a Selenium automation script in Python to validate search functionality on the **Selenium Playground** website.

> [!NOTE]
> **Deliverables:**
> 1. A Python script (`qa_selenium_test.py`) that:
>    - Navigates to the [Selenium Playground Table Search Demo](https://www.lambdatest.com/selenium-playground/table-sort-search-demo).
>    - Locates and interacts with the search box to search for "New York".
>    - Validates that the search results show **5 entries out of 24 total entries**.
> 2. A brief **README** explaining the approach and how to run the script.
> 3. Any additional setup instructions (e.g., local environment, dependencies, drivers etc).

> [!TIP]
> Use Python's `pytest` framework to structure your test cases.

> [!IMPORTANT]
> - **Environment Setup:** Follow good coding practices and ensure the script is compatible with the latest stable Selenium version.
> - **Browser Compatibility:** Test with at least one major browser (e.g., Chrome, Firefox).

> [!CAUTION]
> - **Assertions:** Ensure all validations use robust assertion statements.
> - **Code Quality:** Follow PEP8 standards for Python code.

import pytest
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.chrome.service import Service
from selenium.webdriver.chrome.options import Options
from webdriver_manager.chrome import ChromeDriverManager

class TestSearchFunctionality:
    @pytest.fixture(scope="class")
    def setup(self):
        """Set up the WebDriver and navigate to the website."""
        chrome_options = Options()
        chrome_options.add_argument("--headless")
        chrome_options.add_argument("--disable-gpu")
        self.driver = webdriver.Chrome(service=Service(ChromeDriverManager().install()), options=chrome_options)
        self.driver.implicitly_wait(10)
        yield
        self.driver.quit()

    def test_search_new_york(self, setup):
        """Test the search functionality for 'New York'."""
        url = "https://www.seleniumeasy.com/test/table-search-filter-demo.html"
        self.driver.get(url)

        # Locate the search box
        search_box = self.driver.find_element(By.ID, "task-table-filter")
        
        # Input "New York" in the search box
        search_box.send_keys("New York")
        
        # Validate the search results
        rows = self.driver.find_elements(By.XPATH, "//table[@id='task-table']/tbody/tr")
        visible_rows = [row for row in rows if row.is_displayed()]
        
        assert len(visible_rows) == 5, f"Expected 5 visible rows, but found {len(visible_rows)}."

        # Confirm total entries
        total_entries = len(rows)
        assert total_entries == 24, f"Expected total entries to be 24, but found {total_entries
import pytest
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.chrome.service import Service
from selenium.webdriver.chrome.options import Options
from webdriver_manager.chrome import ChromeDriverManager

class TestSearchFunctionality:
    @pytest.fixture(scope="class")
    def setup(self):
        """Set up the WebDriver and navigate to the website."""
        chrome_options = Options()
        chrome_options.add_argument("--headless")
        chrome_options.add_argument("--disable-gpu")
        self.driver = webdriver.Chrome(service=Service(ChromeDriverManager().install()), options=chrome_options)
        self.driver.implicitly_wait(10)
        yield
        self.driver.quit()

    def test_search_new_york(self, setup):
        """Test the search functionality for 'New York'."""
        url = "https://www.seleniumeasy.com/test/table-search-filter-demo.html"
        self.driver.get(url)

        # Locate the search box
        search_box = self.driver.find_element(By.ID, "task-table-filter")
        
        # Input "New York" in the search box
        search_box.send_keys("New York")
        
        # Validate the search results
        rows = self.driver.find_elements(By.XPATH, "//table[@id='task-table']/tbody/tr")
        visible_rows = [row for row in rows if row.is_displayed()]
        
        assert len(visible_rows) == 5, f"Expected 5 visible rows, but found {len(visible_rows)}."

        # Confirm total entries
        total_entries = len(rows)
        assert total_entries == 24, f"Expected total entries to be 24, but found {total_entries}."

import pytest
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.chrome.service import Service
from selenium.webdriver.chrome.options import Options
from webdriver_manager.chrome import ChromeDriverManager

class TestSearchFunctionality:
    @pytest.fixture(scope="class")
    def setup(self):
        """Set up the WebDriver and navigate to the website."""
        chrome_options = Options()
        chrome_options.add_argument("--headless")
        chrome_options.add_argument("--disable-gpu")
        self.driver = webdriver.Chrome(service=Service(ChromeDriverManager().install()), options=chrome_options)
        self.driver.implicitly_wait(10)
        yield
        self.driver.quit()

    def test_search_new_york(self, setup):
        """Test the search functionality for 'New York'."""
        url = "https://www.seleniumeasy.com/test/table-search-filter-demo.html"
        self.driver.get(url)

        # Locate the search box
        search_box = self.driver.find_element(By.ID, "task-table-filter")
        
        # Input "New York" in the search box
        search_box.send_keys("New York")
        
        # Validate the search results
        rows = self.driver.find_elements(By.XPATH, "//table[@id='task-table']/tbody/tr")
        visible_rows = [row for row in rows if row.is_displayed()]
        
        assert len(visible_rows) == 5, f"Expected 5 visible rows, but found {len(visible_rows)}."

        # Confirm total entries
        total_entries = len(rows)
        assert total_entries == 24, f"Expected total entries to be 24, but found {total_entries}."

import pytest
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.chrome.service import Service
from selenium.webdriver.chrome.options import Options
from webdriver_manager.chrome import ChromeDriverManager

class TestSearchFunctionality:
    @pytest.fixture(scope="class")
    def setup(self):
        """Set up the WebDriver and navigate to the website."""
        chrome_options = Options()
        chrome_options.add_argument("--headless")
        chrome_options.add_argument("--disable-gpu")
        self.driver = webdriver.Chrome(service=Service(ChromeDriverManager().install()), options=chrome_options)
        self.driver.implicitly_wait(10)
        yield
        self.driver.quit()
def test_search_new_york(self, setup):
        """Test the search functionality for 'New York'."""
        url = "https://www.seleniumeasy.com/test/table-search-filter-demo.html"
        self.driver.get(url)
 search_box = self.driver.find_element(By.ID, "task-table-filter")
 search_box.send_keys("New York")
        
        # Validate the search results
        rows = self.driver.find_elements(By.XPATH, "//table[@id='task-table']/tbody/tr")
        visible_rows = [row for row in rows if row.is_displayed()]
        
        assert len(visible_rows) == 5, f"Expected 5 visible rows, but found {len(visible_rows)}."

         # Confirm total entries
        total_entries = len(rows)
        assert total_entries == 24, f"Expected total entries to be 24, but found {total_entries}."
if __name__ == "__main__":
    pytest.main(["-v", "-s", "qa_selenium_test.py"])
