![image](https://github.com/user-attachments/assets/49d01d44-b410-42ad-a46b-a9629f3c98ec)

- Roles of Different elements
  - ![image](https://github.com/user-attachments/assets/9f88da80-024d-4895-b5a3-f41baccafa17)

- Finding by Accessible Names (The normal getByRole() will not work because we will get 2 matches, but we're supposed to get only 1 match)
  - ![image](https://github.com/user-attachments/assets/fc9db42f-0926-4a11-9e13-c4e3623ad3aa)
  - For <input/> tags (because they are self closing), their accessible name is the label they are associated with.
  - To add custom accessible names in any case, we use an aria-label="accessible name" attribute in the tag that we want to find or get. 
