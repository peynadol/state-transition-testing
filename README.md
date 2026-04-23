# State Transition Testing - Makers Bank Challenge

This README documents my work for the Makers Bank sign-up and usage challenge. It includes the states and events I identified, a state transition table, state diagram, test cases, and an Excalidraw screenshot showing my drafts.

## States
1. Account does not exist - No record of this account in the database
2. Account registered - Email exists in database, user is not logged in
3. Account logged in - User is active
4. Account suspended - User is temporarily blocked, e.g too many failed login attempts
6. Account deleted - Account permanently removed, no transitions out

## Events
1. User creates account
2. User logs in
3. User logs out
4. User enters incorrect credentials
5. User enters incorrect credentials three times
6. User confirms identity
7. User deletes account
8. Bank deletes account

## State Transition Table
| Initial State | Event | Next State |
|---|---|---|
| Account does not exist | User creates account | Account registered |
| Account registered | User logs in | Account logged in |
| Account registered | User enters incorrect credentials | Account registered |
| Account registered | User enters incorrect credentials three times | Account suspended |
| Account registered | Bank deletes account | Account deleted |
| Account suspended | User confirms identity | Account registered |
| Account logged in | User logs out | Account registered |
| Account logged in | User deletes account | Account deleted |
| Account logged in | Bank deletes account | Account deleted |

## State Transition Diagram
<img width="1570" height="1652" alt="image" src="https://github.com/user-attachments/assets/41f3d50a-7b16-4043-a729-1d435e6bec36" />

## Test Cases
### Test Case 1 - Main Journey
1. Start - account does not exist
2. User creates account => account registered
3. User enters incorrect credentials => account registered
4. User enters incorrect credentials three times => account suspended
5. User confirms identity => account registered
6. User logs in => account logged in
7. User logs out => account registered
8. User logs in => account logged in
9. User deletes account => account deleted

### Test Case 2 - Bank deletes account (user logged in)
1. Start - account logged in
2. Bank deletes account => account deleted

### Test Case 3 - Bank deletes account (user registered, not logged in)
1. Start - account registered
2. Bank deletes account => account deleted

## Working notes from Excalidraw
<img width="2968" height="1474" alt="image" src="https://github.com/user-attachments/assets/98b2b611-8673-44fb-953b-b5c8da842f31" />
<img width="2232" height="1626" alt="image" src="https://github.com/user-attachments/assets/9f7506ee-77e0-40e4-916a-013433d239d4" />



