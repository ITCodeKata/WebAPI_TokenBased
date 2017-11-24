# WebAPI_TokenBased

Step1: Install PostMan on chrome


Step2: Run the application. Get end url (Ignore if no default page loads)


Step3: Check for anonomus request (without authentication)

http://localhost:55999/api/data/forall (Should work for all - correct the port)


Step4.1: Admin access token generation http://localhost:55999/token
Body: 
username: admin
password: admin
grant_type: password

responce: 

{
    "access_token": "iF4PvODwIkTZImhMqE4zUhg_1ehe9aGKbOmq7poArf5bRAq7dBft5O0IHs_1RaJo7z7tC2rErBScFllIuGcwA7ZKu7EV7riN7dfL32wd98E94damN6zmZmxob8jyy-PxaFRMAPBGuzQTxpGvOu5-EeQQ9f2elGKqVRie48N7Szoe4vae80Uyd5hGo1yorXbYb939_sq5XWjTDncegTijX4zHAm_zIQ78XqH6FaLztPxZOaIS77V_zjS64Y0aYK196XHDH918E_6gIAdbcBJridf-LO8Ix8_wnMB_-e4aZ9_AP7mUxv5a43uqzyfn6YzylHKvRKzh_yZLObYHlBg1ew",
    "token_type": "bearer",
    "expires_in": 86399
}


Step4.2: Admin request methord - api/data/authorize - http://localhost:55999/api/data/authorize && http://localhost:55999/api/data/authenticate
Header-> Authorization : bearer iF4PvODwIkTZImhMqE4zUhg_1ehe9aGKbOmq7poArf5bRAq7dBft5O0IHs_1RaJo7z7tC2rErBScFllIuGcwA7ZKu7EV7riN7dfL32wd98E94damN6zmZmxob8jyy-PxaFRMAPBGuzQTxpGvOu5-EeQQ9f2elGKqVRie48N7Szoe4vae80Uyd5hGo1yorXbYb939_sq5XWjTDncegTijX4zHAm_zIQ78XqH6FaLztPxZOaIS77V_zjS64Y0aYK196XHDH918E_6gIAdbcBJridf-LO8Ix8_wnMB_-e4aZ9_AP7mUxv5a43uqzyfn6YzylHKvRKzh_yZLObYHlBg1ew
Type: GET

responce: 
"HelloAdmin as: Gaurav Sharma Role:admin"



Step 5.1: User access token generation http://localhost:55999/token
Body: 
username: user
password: user
grant_type: password

responce: 

{
    "access_token": "lmW1moRIhyapXu7L6y2Q3K1gX6Wwavb9P54B8nlDr1RitHsW4h976Bmdo9g_9R_DwsF5SaDeXyvWSZ2Wj9p2SSU1irGfiLk7L4-yBVgK71beX_ysdqpcgs4vF-hGjV5VlEIaR7lAQjBpJ5hCHj2NyhAADRjjily-on0fEr_iFJfLFRWjA2sqMi9InaIeGmvUOqamfdtEVkDhFekSP0dMFu3ShgjQyo2GgufOs8f8cNfFjgQkogDRyn4xBlLrracYglM-s0KaacVx_4rWe0_CcbLFgZLOZ4atgs7J3k7qk4yFh43bxreytvBFQLWQAAyXWbuMJw9BQuh6PIc-ZrfhyA",
    "token_type": "bearer",
    "expires_in": 86399
}

Step5.2: Admin request methord - api/data/authorize - http://localhost:55999/api/data/authenticate 
Header-> Authorization : bearer lmW1moRIhyapXu7L6y2Q3K1gX6Wwavb9P54B8nlDr1RitHsW4h976Bmdo9g_9R_DwsF5SaDeXyvWSZ2Wj9p2SSU1irGfiLk7L4-yBVgK71beX_ysdqpcgs4vF-hGjV5VlEIaR7lAQjBpJ5hCHj2NyhAADRjjily-on0fEr_iFJfLFRWjA2sqMi9InaIeGmvUOqamfdtEVkDhFekSP0dMFu3ShgjQyo2GgufOs8f8cNfFjgQkogDRyn4xBlLrracYglM-s0KaacVx_4rWe0_CcbLFgZLOZ4atgs7J3k7qk4yFh43bxreytvBFQLWQAAyXWbuMJw9BQuh6PIc-ZrfhyA
Type: GET

responce: 
"HelloUser as: Amit Sharma"

&& http://localhost:55999/api/data/authorize

responce
HTTP status: 403 Forbidden
