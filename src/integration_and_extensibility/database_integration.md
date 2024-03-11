# Database Integration

pace is designed to be an offline-first application, meaning that it does not
require an internet connection to function. However, it is possible to integrate
pace with a database to enable features such as data synchronization across
multiple devices, data backup, and data recovery.

**Note**: This feature is not yet implemented. It is planned for a future
release. So far, pace only supports local storage of activity logs in a
file-based format. This section provides an overview of the planned database
integration feature and how it will work.

## Vision

The vision for database integration is to provide a way to store activity logs
in a database, such as SQLite, PostgreSQL, or MySQL. This will enable the
following features:

- **Data Synchronization**: Activity logs can be synchronized across multiple
  devices, so that you can access your data from anywhere and keep it up to
  date.

- **Data Backup**: Activity logs can be backed up to a remote server or cloud
  storage service, so that you can recover your data in case of loss or
  corruption.

- **Data Recovery**: Activity logs can be recovered from a backup, so that you
  can restore your data to a previous state.

- **Data Sharing**: Activity logs can be shared with other users, so that you
  can collaborate on projects and activities.

- **Data Security**: Activity logs can be encrypted and protected with access
  controls, so that your data is safe from unauthorized access.

- **Data Privacy**: Activity logs can be stored in compliance with privacy
  regulations, so that your data is protected and respected.

- **Data Integrity**: Activity logs can be verified and validated, so that you
  can trust that your data is accurate and reliable.

## Implementation

The implementation of database integration will involve the following
components:

- **Database Adapter**: The `Storage` trait will be implemented for a database
  storage. We will start out with SQLite to provide a simple and portable
  solution. The `Storage` trait already has a `FileStorage` and
  `InMemoryStorage` implementation, so we will add a `DatabaseStorage`
  implementation. The `DatabaseStorage` will be a thin wrapper around the
  `diesel` ORM, providing a simple interface for storing and retrieving activity
  logs in a database. This adapter will support different database backends,
  such as SQLite, PostgreSQL, and MySQL.

- **Data Synchronization**: A synchronization service will be developed to
  enable data synchronization across multiple devices. This service will use a
  client-server architecture, with a server component for storing and managing
  activity logs, and a client component for interacting with the server. We will
  use `axum` and `tokio` to develop the server and client components.

- **Data Backup and Recovery**: A backup and recovery service will be developed
  to enable data backup to a remote server or cloud storage service, and data
  recovery from a backup. This service will use a client-server architecture,
  similar to the synchronization service. We will use `reqwest` and `opendal` to
  interact with remote servers and cloud storage services.

- **Data Sharing**: A sharing service will be developed to enable sharing of
  activity logs with other users. For this feature, we will use a combination of
  the synchronization service and the backup and recovery service. We will also
  implement access controls to manage sharing permissions. This will be a more
  advanced feature, and we will build the team collaboration feature on top of
  it.

- **Data Security and Privacy**: Security and privacy features will be
  implemented to protect activity logs from unauthorized access and ensure
  compliance with privacy regulations.

- **Data Integrity**: Integrity features will be implemented to verify and
  validate activity logs, and to ensure that they are accurate and reliable.
