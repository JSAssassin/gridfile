# GridFile - Mongoose Schema for MongoDB GridFS
GridFile is a reusable [Mongoose](https://mongoosejs.com/) schema for [MongoDB GridFS](https://docs.mongodb.com/manual/core/gridfs/). No separate database setup is needed as it uses the Mongoose connection for interacting with GridFS.

# Installation
```bash
npm install gridfile
```

# Usage
- Import the schema
```javascript
const schema = require('gridfile')
```

- Create a Mongoose model from the schema
```javascript
const GridFile = mongoose.model('GridFile', schema)
```

- Upload a file
```javascript 
const fileStream = fs.createReadStream('/path/to/file.ext')

const gridFile = new GridFile()
gridFile.filename = 'file.ext'
await gridFile.upload(fileStream)
```
- Download a file
```javascript
const fileStream = fs.createWriteStream('/path/to/file.ext')
const gridFile = GridFile.findById('id')

await gridFile.download(fileStream)
```

## Examples
Few examples are available in the [examples](examples) directory.

# Documentation
Documentation is available at [API.md](API.md)

# Fixes & Improvements
Head over to the issues tab at [github.com](https://github.com/abskmj/gridfile/issues) to report a bug or suggest an improvement. Feel free to contribute to the code or documentation by creating a pull request.

# Sponsor / Support
If you find the project interesting or helpful, please consider sponsoring or supporting it at [github.com](https://github.com/abskmj/gridfile).