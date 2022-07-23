# ads-client-test-plc-project
A PLC project used for ads-client testing. 

## How to test `ads-client`
1. Clone this repository
2. Open AdsClientTests.sln in TwinCAT XAE
3. Activate configuration and download sofware
4. Set PLC to run
6. Clone `ads-client` repository
5. Run `npm test` command inside ads-client directory

## Example output 
```
> ads-client@1.14.0 test
> jest --runInBand

 PASS  test/ads-client.test.js
  √ IMPORTANT NOTE: This test requires running a specific PLC project locally (https://github.com/jisotalo/ads-client-test-plc-project) (1 ms)
  connection
    √ client is not connected at beginning (2 ms)
    √ checking ads client settings (2 ms)
    √ connecting to localhost and 851 (89 ms)
    √ checking that test PLC project is active (13 ms)
    √ checking that test PLC project version is correct (9 ms)
  resetting PLC to original state
    √ resetting PLC (11 ms)
    √ checking that reset was succesful (6 ms)
    √ setting IsReset to false (5 ms)
    √ checking that test PLC project is running (4 ms)
  basic tests
    √ reading system manager state (5 ms)
    √ reading plc runtime state (4 ms)
    √ reading device info (3 ms)
  reading values
    √ reading INT (8 ms)
    √ reading STRING (5 ms)
    √ reading STRUCT (15 ms)
    √ reading TIME_OF_DAY (9 ms)
    √ reading ENUM as object (13 ms)
    √ reading ENUM as number (11 ms)
    √ reading UNION STRING value (15 ms)
    √ reading UNION REAL value (4 ms)
    √ reading ARRAY OF INT (10 ms)
    √ reading ARRAY OF STRUCT (6 ms)
    √ reading ARRAY[-100..100] OF LREAL (12 ms)
    √ reading ARRAY[1..3, 1..2] OF BYTE (multi dimensional) (9 ms)
    √ reading ARRAY[1..3] OF ARRAY[1..2] OF SINT (multi dimensional) (10 ms)
    √ reading FUNCTION BLOCK (9 ms)
    √ reading POINTER target value (4 ms)
    √ reading REFERENCE target value (4 ms)
    √ reading and comparing pack-mode struct sizes (4 ms)
    √ reading STRUCT with pack-mode 1 (28 ms)
    √ reading STRUCT with pack-mode 8 (6 ms)
  writing values
    √ writing INT (9 ms)
    √ writing STRING (5 ms)
    √ writing STRUCT (6 ms)
    √ writing STRUCT (without autoFill -> should throw error) (140 ms)
    √ writing STRUCT (with autoFill) (8 ms)
    √ writing TIME_OF_DAY (3 ms)
    √ writing ENUM as string (5 ms)
    √ writing ENUM as number (4 ms)
    √ writing UNION STRING value (6 ms)
    √ writing UNION REAL value (7 ms)
    √ writing ARRAY OF INT (6 ms)
    √ writing ARRAY OF STRUCT (3 ms)
    √ writing ARRAY[-100..100] OF LREAL (32 ms)
    √ writing ARRAY[1..3, 1..2] OF BYTE (multi dimensional) (8 ms)
    √ writing ARRAY[1..3] OF ARRAY[1..2] OF SINT (multi dimensional) (3 ms)
    √ writing FUNCTION BLOCK (3 ms)
    √ writing POINTER target value (7 ms)
    √ writing REFERENCE target value (5 ms)
    √ writing STRUCT with pack-mode 1 (9 ms)
    √ writing STRUCT with pack-mode 8 (6 ms)
  Remote procedure calls (RPC)
    √ calling simple RPC method (16 ms)
    √ calling RPC method with structs (6 ms)
  issue specific tests
    issue 94 (https://github.com/jisotalo/ads-client/issues/94)
      √ writing value and reading it (13 ms)
  finalizing
    √ disconnecting (5 ms)

Test Suites: 1 passed, 1 total
Tests:       56 passed, 56 total
Snapshots:   0 total
Time:        2.48 s
Ran all test suites.
```
