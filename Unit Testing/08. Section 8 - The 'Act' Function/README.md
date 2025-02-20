- Router Contexts are not straightforward and cause issues when you want to test components that have "Link" etc.
  -  ![image](https://github.com/user-attachments/assets/862ccc0b-eee4-41aa-9294-16510641f8bc)
 
- This is how you can wrap your rendered component in a `MemoryRouter`
  - ![image](https://github.com/user-attachments/assets/2d958ade-6c62-47c4-be37-e7b6e80e72b0)

 - ![image](https://github.com/user-attachments/assets/f3ca71ea-5fa9-407e-b371-e6e7e82c3008)

- act() function is used to andle or work wit async functions or requests
 - ![image](https://github.com/user-attachments/assets/f316d9ef-96bd-4064-9164-c15b0aeff3f5)
- But don't directly use "act()". Use of these techniques-
  - ![image](https://github.com/user-attachments/assets/72dfe5bf-78f3-4e81-9fa1-29505cf9035f)
  - ![image](https://github.com/user-attachments/assets/5b8dca75-ab34-40a4-87c0-1eee7698dbc2)
 
- act() is originally created by 'react-router-dom' but is imported, then modified and exported again by the 'testing-li
