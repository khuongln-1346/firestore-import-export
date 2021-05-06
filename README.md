# Firestore Import Export
A script that help to import in Cloud Firestore

# Requirements

You need [NODE](https://nodejs.org/en/download/) or something that can run JAVASCRIPT (JS) file.

Get **serviceAccount** JSON file from *Project Setting > SERVICE ACCOUNTS* in Firebase Console

# Setting Up

Download or clone this repository

```
git clone https://github.com/khuongln-1346/firestore-import-export.git
```

Install NPM packages

```
npm install
```

# Import data to Firestore

This will import a collection to Firestore will overwrite any documents in that collection with matching id's to those in your json.

If you have date type, location type in your JSON, please add fields to the command line. **The date, geo and autoid arguments is optional**.

If you need generate auto document ID, please add `autoid=true` to the command line. Default `autoid=false`
```
node import.js import-to-firestore.json date=created_at,updated_at geo=location autoid=true
```

Sample from __import-to-firestore.json__. "test" will be the sub collection name. The date type will have _seconds and _nanoseconds in it.

```
{
  "/parents/child/test":{
    "first-key":{
      "email":"test@example.com",
      "test_number": 1,
      "test_array": ["value1", "value2", "value3"],
      "website":"example.com",
      "custom":{
        "firstName":"Naruto",
        "lastName":"Uzumaki"
      },
      "created_at":{
        "_seconds":1534046400,
        "_nanoseconds":0
      },
      "updated_at":{
        "_seconds":1534046400,
        "_nanoseconds":0
      },
      "location":{
        "_latitude":49.290683,
        "_longitude":-123.133956
      }
    },
    "second-key":{
      "email":"hi@example.com",
      "website":"google.com",
      "custom":{
        "firstName":"Harry",
        "lastName":"Potter"
      },
      "created_at":{
        "_seconds":1534046400,
        "_nanoseconds":0
      },
      "updated_at":{
        "_seconds":1534046400,
        "_nanoseconds":0
      },
      "location":{
        "_latitude":49.290683,
        "_longitude":-123.133956
      }
    }
  }
}
```

*If you have any recommendation or question, please create an issue. Thanks,*

# Thanks to
+ https://github.com/dalenguyen/firestore-import-export
