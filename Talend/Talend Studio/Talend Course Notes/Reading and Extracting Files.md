# Reading and Extracting Files
##### Steps to process and read data
- Identify file properties
	- Identify the file properties correctly in order to determine how to extract
	- Check the structure of the delimited or hierarchical file
- Define Schema
	- Mapping the data to a column
	- Build manually or import a schema 
- Read File
	- Use a dedicated component to read from source file
	- Configure using file properties and the schema

##### CSV files

- An example csv file with a <text style="color:cyan"> comma field separator </text> and a <text style="color:cyan"> new line row separator</text>
- The first row are the table headers

  ```
  First,Last,Street,City
  fName_1,lName_1,street_1,city_1
  fName_2,lName_2,street_2,city_2
  ```

##### XML Files

- Has a recursive structure and stored in a tree of nodes
- Tags are case sensitive 
- Use XPath to get the nodes in the file 
  - For example, to get `<Products>` you would use `root/row/Product`

  ```XML
  <root>
    <row>
      <ShopName>Shop1</ShopName>
      <Quantity>200</Quantity>
      <Product>Product 23</Product>
    </row>
    <row>
      <ShopName>Shop2</ShopName>
      <Quantity>300</Quantity>
      <Product>Product 43</Product>
    </row>
  </root>
  ```

##### JSON

- Uses objects and arrays
- Use JSON queries to map data

```JSON
{
  "ShopSales" : 
  [
    {
      "ShopName" : "Shop1",
      "Quantity" : 200,
      "Product" : "Product 23"
    },
    {
      "ShopName" : "Shop2",
      "Quantity" : 300,
      "Product" : "Product 43"
    },
  ]
}
```