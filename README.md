# Authenticator

Is an authentication service. This service will handle signing up and signing in process whether using phone number, email or social media.

## Prerequisites

### Dependencies

- Go - Programming Language
- PostgreSQL - User Data persistent storage system
- Redis - User Data caching system
- Firebase - Google Account integration

#### Service Dependencies

- Tokenizer Service

### Transport/Delivery/Communication Channel

- GRPC
- HTTP2
- HTTP
- CLI

### Data Structure

#### users table

| Fields        | type          | Nullable  | Description                                       |
| ------------- | --------------| ----------| --------------------------------------------------|
| id            | uuid string   | no        | generated with *Sonyflake*                        |
| type          | string        | no        | generated by system                               |
| country_id    | string        | no        | from user input, validated by geolocation service |
| phone_number  | string        | no        | from user input                                   |
| name          | string        | no        | from user input                                   |
| salutation    | string        | yes       | from user input                                   |
| email         | string        | yes       | from user input                                   |
| status        | string        | no        | updated by system                                 |
| level         | string        | no        | generated by system, tier 1, level 1              |
| created_at    | datetime      | no        | generated by system                               |
| updated_at    | datetime      | no        | generated by system                               |

#### status_histories table

| Fields        | type          | Nullable  | Description                                       |
| ------------- | --------------| ----------| --------------------------------------------------|
| id            | uuid string   | no        | generated with *Sonyflake*                        |
| user_id       | string        | no        | generated by system                               |
| status        | datetime      | no        | generated by system                               |
| updated_at    | datetime      | no        | generated by system                               |

#### otps table

| Fields        | type          | Nullable  | Description                                       |
| ------------- | --------------| ----------| --------------------------------------------------|
| user_id       | uuid string   | no        | generated with *Sonyflake*                        |
| otp           | string        | no        | generated by system                               |
| created_at    | datetime      | no        | generated by system                               |
| expired_at    | datetime      | no        | generated by system                               |

#### login_states table

| Fields        | type          | Nullable  | Description                                       |
| ------------- | --------------| ----------| --------------------------------------------------|
| user_id       | uuid string   | no        | generated with *Sonyflake*                        |
| logged_in_on  | string        | no        | generated by system                               |
| logged_in_from| string        | no        | generated by system                               |
| logged_in_ip  | string        | no        | generated by system                               |
| status        | string        | no        | generated by system                               |
| logged_in_at  | datetime      | no        | generated by system                               |
| logged_out_at | datetime      | no        | generated by system                               |

## How to build as docker image

## How to run as container

## How to develop

### How to provision the environment

### How to run migration

### Run as container

## How to deploy to a certain environment using automation

### How to provision infrastructure

### How to run the DB Migration
