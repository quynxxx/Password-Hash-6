# Password-Hash-6
Password Hash.sol
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract PasswordHash {
    bytes32 private passwordHash;

    constructor(string memory _password) {
        passwordHash = keccak256(abi.encodePacked(_password));
    }

    function checkPassword(string memory _input) public view returns (bool) {
        return keccak256(abi.encodePacked(_input)) == passwordHash;
    }
}
