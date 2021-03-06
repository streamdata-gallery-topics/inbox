swagger: "2.0"
x-collection-name: Plentymarkets
x-complete: 1
info:
  title: plentymarkets REST-API
  description: the-plentymarkets-rest-api-expands-the-functionality-of-the-plentymarkets-cms-and-allows-access-to-resources-i-e--data-records-via-unique-uri-paths
  contact:
    name: plentymarkets
    url: https://forum.plentymarkets.com/c/rest-api
  version: 1.0.0
host: example.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /rest/storage/plugins/inbox:
    delete:
      summary: Delete files from the inbox
      description: Deletes a list of files from the inbox. A list of storage keys
        must be specified.
      operationId: deleteRestStoragePluginsInbox
      x-api-path-slug: reststoragepluginsinbox-delete
      parameters:
      - in: query
        name: keyList
        description: List of storage keys for the files to be deleted
      responses:
        200:
          description: OK
      tags:
      - Files
      - From
      - Inbox
    post:
      summary: Upload a file to the inbox
      description: Uploads a file to the inbox. The storage key (i.e. file path) must
        be specified.
      operationId: postRestStoragePluginsInbox
      x-api-path-slug: reststoragepluginsinbox-post
      parameters:
      - in: query
        name: key
        description: The storage key for the file to upload
      responses:
        200:
          description: OK
      tags:
      - Upload
      - File
      - To
      - Inbox
  /rest/storage/plugins/inbox/list:
    get:
      summary: List files from the inbox
      description: |-
        Lists all files of all plugins stored in the inbox. A prefix can be specified to list all files of a specific
        plugin folder only.
      operationId: getRestStoragePluginsInboxList
      x-api-path-slug: reststoragepluginsinboxlist-get
      parameters:
      - in: query
        name: prefix
        description: Prefix to list all files of a specific plugin folder only
      responses:
        200:
          description: OK
      tags:
      - List
      - Files
      - From
      - Inbox
  /rest/storage/plugins/inbox/object-url:
    get:
      summary: Get the content of a file from the inbox
      description: Gets the content of a file stored in the inbox. The storage key
        (i.e. file path) must be specified.
      operationId: getRestStoragePluginsInboxObjectUrl
      x-api-path-slug: reststoragepluginsinboxobjecturl-get
      parameters:
      - in: query
        name: key
        description: The storage key for the file to retrieve
      responses:
        200:
          description: OK
      tags:
      - Content
      - Of
      - File
      - From
      - Inbox