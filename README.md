This is an NPM package for Tables, Created with ❤️ By [Dhavan Singhal](https://www.linkedin.com/in/dhavan-singhal-a6742b14a/).

# What It Is

With this NPM Package you can change your normal table with Datatable. Now You may be wonder what is a Datatable? the Datatable is a table with some filters like Search Option, Filter with date. you can edit or delete a row and with the help of callback function you can save the change in database<br/> that's it???<br/> No!! you can hide a row or you can print the table or you can export the table as a pdf file and also you can sort any row in asec and desc orders.

### How to use it
<br/> 

`npm install myreacttable`
<br/>
this command is all you need to install the npm package in your project.<br/>
Now you must be wonder about the depandancies <br/>
it is where the sad part came, this npm package is only for react project till now <br/>
and you need two preinstall npm packages to use this package. Those package are given below:<br/>
   <br/>
["bootstrap": "^4.5.2"](https://www.npmjs.com/package/bootstrap){:target="_blank"} : install this package with `npm install bootstrap` command <br/>
i use this package for make the table responsive 
<br/>
<br/>
["framer-motion": "^2.6.0"](https://www.npmjs.com/package/framer-motion) : install this package with `npm install framer-motion` command <br/>
i use this package for creating some animation ,if you want you can skip this but for that you have to modify the package file.
<br/><br/>

## Don't Like The Table UI?

although i tried my best to make the UI look Good and Simple. and this table is responsive as well. <br/>
but if you still reading this than i think you don't like UI, do you??<br/>
you don't have to answer that question. Yes!! you can modify the design the way you want.<br/>
for make this process easy for you i attached an ID with almost every element. you can refer the Below Picture For that.

   <br/>
   
  ![Alt text](img/id_reference_images.jpg?raw=true "ID Reference")

# How to use this

after installing the dependencies and this package, you can use this table like the below code<br/><br/>
```
    import MyReactTable from "myreacttable";

    const initialColumnProps = [
    {
        Header: "Name",
        id: "name_id",
        type:'text',
        Filter: "Search",
    },
    {
        Header: "Order",
        id: "order",
        type:'number',
        Filter: false,
    },
    {
        Header: "Status",
        id: "status",
        type:'select',
        Filter: "Dropdown",
        option:["On process","Complete","Failed","Pending"]
    },
    {
        Header: "Date",
        id: "date",
        type:'date',
        Filter: "daterange",
    },
    ];

    const initialDataProps = [
        ["I", 53,"Pending","11-1-2021", 0 ]
        ["A", 77,"Pending","18-1-2021", 1 ]
        ["C", 34,"Complete","31-1-2021", 2 ]
        ["B", 98,"Complete","21-3-2021", 3 ]
        ["E", 43,"Pending","13-2-2021", 4 ]
        ["F", 67,"Complete","12-3-2021", 5 ]
        ["G", 76,"Complete","22-3-2021", 6 ]
        ["H", 45,"Pending","11-2-2021", 7 ]
        ["Z", 87,"Complete","16-3-2021", 8 ]
        ["X", 65,"Pending","17-2-2021", 9 ]
        ["Y", 23,"Pending","28-3-2021", 10 ]
        ["W", 12,"Complete","27-2-2021", 11 ]
        ["Q", 54,"Complete","31-1-2021", 12 ]
    ];

    handleDataDelete = (data) => {
        this.setState({dataDelete : data})
    }

    handleDataEdit = (data) => {
        this.setState({dataEdit : data})
    } 

    <MyReactTable 
            onDataDelete={this.handleDataDelete} 
            onDataEdit={this.handleDataEdit} 
            columns={initialColumnProps}
            data={initialDataProps}
            editButton={true}
            deleteButton={true}
            />
```

## Options
### Filters
Filter will be added in columns for use a filter for that particular column
  **Search Option**<br/>
    This option will help you to search a value in the particular row<br/>
    You can Use this by Providing the Value `Search` in `Filter` key on column data Object in respective column value.<br/>
  **Dropdown Option**<br/>
    This option will filter all the unqiuq value and provide you an option to filter the data based on those values. Like in case you have a status column in your data and you use the Dropdown filter for that columne it'll help the user to filter the data based on all the Status available in the data.<br/>
    You can Use this by Providing the Value `Dropdown` in `Filter` key on column data Object in respective column value.<br/>
  **Daterange Option**<br/>
    This option will helo you to filter the data based on the date. This option can only use for a column which have dates. if you have any other type of value like number or string in that row then it will give you a error<br/>
    You can Use this by Providing the Value `Daterange` in `Filter` key on column data Object in respective column value.<br/>

### Data types
type will be added in columns if you are using edit option when the user click on edit button it will help to under what input need to be taken from the user for that particular column. we have four types available.
  **text**<br/>
    It will take all kind of values. It can be alphabet, numbers or any symbol .<br/>
    You can Use this by Providing the Value `text` in `type` key on column data Object in respective column value.
  **Date**<br/>
    This will take only date value.<br/>
    You can Use this by Providing the Value `date` in `type` key on column data Object in respective column value.<br/>
  **Number**<br/>
    This will take numbers only<br/>
    You can Use this by Providing the Value `number` in `type` key on column data Object in respective column value.<br/>
  **Select**<br/>
    if you use select as a type than it will ask user to select a value from a dropdown. The dropdown will be automatically generated from the unquie values available in the table in that column or you can provide those values from which you want the user to select a value by providing a array of values in `option` key on column<br/>
    You can Use this by Providing the Value `select` in `type` key on column data Object in respective column value.<br/>

### Hide/Show Edit or Delete Option
you can hide the edit or delete option from the table if you dont want it by providing `false` value in `editButton` and `deleteButton` props respectively. By default the value will be `true` for these two props.<br/>
if the edit option or delete option is true than you need to provide a extra column in each row in data object that will uniquely identify that row (primary key). if both option are set to false than you don't have to provide this extra column in data object otherwise it will through the error or vice verse.

### Get Edit or Delete row by callback function
you can get the row that is being edited or deleted by the user by providing a funtion in `onDataEdit` and `onDataDelete` props respectively.

**Note: raise and issue for any problem you face!**
