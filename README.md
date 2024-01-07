# Fix register & add token issue

## Prerequisite
Make sure you install docker, nvm in your local environment. Switch your node version to 16.  

Follow the [instruction](https://support.google.com/accounts/answer/185833?hl=en) to get your app password and replace the `EMAIL_PWD` on `skill-test/backend/.env`

## Initialization
1. Start the db via docker 
```bash
skill-test $ cd backend/src/db
skill-test/backend/src/db $ docker compose up
```

2. Insert mock data into db  
2.1 Open the browser and navigate to localhost:8080  
2.2 Login to MySQL (account info is in docker-compose.yml)  
2.3 Copy the sql script on skill-test/backend/src/db/new_mgldefi.sql and paste on MySQL gui to insert mock data  

3. Start frontend and backend server  
3.1 Open a new terminal and execute the following command
```bash
skill-test $ npm run dev
```

## Register
1. Open the client side (navigate to localhost:3000)  
2. Click the register button to finish the registration
3. When finishing the registration, you will be asked to bind a wallet by accessing the existing one or creating a new wallet

## Add ETH token on profile page
1. You will be redirected to profile page once all the registration process is done
2. Click the Add Token button in your profile page
3. Enter the ETH token address `0x2170Ed0880ac9A755fd29B2688956BD959F933F8`
4. The ETH price will be displayed later

## Improvement
There're many redundant code in this project, should be removed to make collaborative developers easy to read

1. Remove unused import in every module or class
2. Remove commented console.log
3. Move all environment variables on `skill-test/src/constants/env.js` to `skill-test/.env`, don't hardcode constants on javascript file
4. The file structure of this project need to modify, should create a frontend folder to store all fronend files, so the modified file structure would be like:
```
.
├── README.md
├── backend
└── frontend
```
This file structure would be neat for both fronend developers and backend developers although this cannot start frontend and backend server at once.