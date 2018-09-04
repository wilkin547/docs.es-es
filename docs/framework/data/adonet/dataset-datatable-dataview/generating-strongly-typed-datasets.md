---
title: Generar conjuntos de datos fuertemente tipados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: 9accfb68c57384e12a59bae40ebe30a2d3e22877
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526493"
---
# <a name="generating-strongly-typed-datasets"></a><span data-ttu-id="7fcdd-102">Generar conjuntos de datos fuertemente tipados</span><span class="sxs-lookup"><span data-stu-id="7fcdd-102">Generating Strongly Typed DataSets</span></span>
<span data-ttu-id="7fcdd-103">A partir de un esquema XML que cumple con el estándar del lenguaje de definición de esquemas XML (XSD), es posible generar un objeto <xref:System.Data.DataSet> fuertemente tipado mediante la herramienta XSD.exe incluida en [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7fcdd-103">Given an XML Schema that complies with the XML Schema definition language (XSD) standard, you can generate a strongly typed <xref:System.Data.DataSet> using the XSD.exe tool provided with the [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)].</span></span>  
  
 <span data-ttu-id="7fcdd-104">(Para crear un xsd a partir de las tablas de base de datos, vea <xref:System.Data.DataSet.WriteXmlSchema%2A> o [trabajar con objetos DataSet en Visual Studio](https://msdn.microsoft.com/library/8bw9ksd6.aspx)).</span><span class="sxs-lookup"><span data-stu-id="7fcdd-104">(To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](https://msdn.microsoft.com/library/8bw9ksd6.aspx)).</span></span>  
  
 <span data-ttu-id="7fcdd-105">El código siguiente muestra la sintaxis para generar un **DataSet** con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="7fcdd-105">The following code shows the syntax for generating a **DataSet** using this tool.</span></span>  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 <span data-ttu-id="7fcdd-106">En esta sintaxis, el `/d` directiva indica a la herramienta para generar un **DataSet**y el `/l:` indica a la herramienta de lenguaje que debe utilizar (por ejemplo, C# o Visual Basic. NET).</span><span class="sxs-lookup"><span data-stu-id="7fcdd-106">In this syntax, the `/d` directive tells the tool to generate a **DataSet**, and the `/l:` tells the tool what language to use (for example, C# or Visual Basic .NET).</span></span> <span data-ttu-id="7fcdd-107">El elemento opcional `/eld` directiva especifica que se puede utilizar [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] para consultar contra generado **conjunto de datos.**</span><span class="sxs-lookup"><span data-stu-id="7fcdd-107">The optional `/eld` directive specifies that you can use [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] to query against the generated **DataSet.**</span></span> <span data-ttu-id="7fcdd-108">Esta opción se utiliza cuando también se especifica la opción `/d`.</span><span class="sxs-lookup"><span data-stu-id="7fcdd-108">This option is used when the `/d` option is also specified.</span></span> <span data-ttu-id="7fcdd-109">Para obtener más información, consulte [Querying Typed DataSets](../../../../../docs/framework/data/adonet/querying-typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="7fcdd-109">For more information, see [Querying Typed DataSets](../../../../../docs/framework/data/adonet/querying-typed-datasets.md).</span></span> <span data-ttu-id="7fcdd-110">Opcional `/n:` directiva indica a la herramienta que genere también un espacio de nombres para el **DataSet** llamado **XSDSchema.Namespace**.</span><span class="sxs-lookup"><span data-stu-id="7fcdd-110">The optional `/n:` directive tells the tool to also generate a namespace for the **DataSet** called **XSDSchema.Namespace**.</span></span> <span data-ttu-id="7fcdd-111">El resultado del comando es XSDSchemaFileName.cs, que se puede compilar y utilizar en una aplicación de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="7fcdd-111">The output of the command is XSDSchemaFileName.cs, which can be compiled and used in an ADO.NET application.</span></span> <span data-ttu-id="7fcdd-112">El código generado puede compilarse como una biblioteca o un módulo.</span><span class="sxs-lookup"><span data-stu-id="7fcdd-112">The generated code can be compiled as a library or a module.</span></span>  
  
 <span data-ttu-id="7fcdd-113">En el siguiente código se muestra la sintaxis para compilar el código generado como una biblioteca mediante el compilador de C# (csc.exe).</span><span class="sxs-lookup"><span data-stu-id="7fcdd-113">The following code shows the syntax for compiling the generated code as a library using the C# compiler (csc.exe).</span></span>  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 <span data-ttu-id="7fcdd-114">La directiva `/t:` indica a la herramienta que compile en una biblioteca mientras que las directivas `/r:` especifican bibliotecas dependientes necesarias para la compilación.</span><span class="sxs-lookup"><span data-stu-id="7fcdd-114">The `/t:` directive tells the tool to compile to a library, and the `/r:` directives specify dependent libraries required to compile.</span></span> <span data-ttu-id="7fcdd-115">El resultado del comando es XSDSchemaFileName.dll, que se puede pasar al compilador al compilar una aplicación de ADO.NET con la directiva `/r:`.</span><span class="sxs-lookup"><span data-stu-id="7fcdd-115">The output of the command is XSDSchemaFileName.dll, which can be passed to the compiler when compiling an ADO.NET application with the `/r:` directive.</span></span>  
  
 <span data-ttu-id="7fcdd-116">En el siguiente código se muestra la sintaxis para tener acceso al espacio de nombres pasado a XSD.exe en una aplicación de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="7fcdd-116">The following code shows the syntax for accessing the namespace passed to XSD.exe in an ADO.NET application.</span></span>  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 <span data-ttu-id="7fcdd-117">En el ejemplo de código siguiente se utiliza un **DataSet** denominado **CustomerDataSet** para cargar una lista de clientes desde el **Northwind** base de datos.</span><span class="sxs-lookup"><span data-stu-id="7fcdd-117">The following code example uses a typed **DataSet** named **CustomerDataSet** to load a list of customers from the **Northwind** database.</span></span> <span data-ttu-id="7fcdd-118">Una vez cargados los datos mediante el **rellenar** método, el ejemplo recorre en bucle cada cliente en el **clientes** con el tipo de tabla **CustomersRow** ( **DataRow**) objetos.</span><span class="sxs-lookup"><span data-stu-id="7fcdd-118">Once the data is loaded using the **Fill** method, the example loops through each customer in the **Customers** table using the typed **CustomersRow** (**DataRow**) object.</span></span> <span data-ttu-id="7fcdd-119">Esto proporciona acceso directo a la **CustomerID** columna, en lugar de a través del **DataColumnCollection**.</span><span class="sxs-lookup"><span data-stu-id="7fcdd-119">This provides direct access to the **CustomerID** column, as opposed to through the **DataColumnCollection**.</span></span>  
  
```vb  
Dim customers As CustomerDataSet= New CustomerDataSet()  
Dim adapter As SqlDataAdapter New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers;", _  
  "Data Source=(local);Integrated " & _  
  "Security=SSPI;Initial Catalog=Northwind")  
  
adapter.Fill(customers, "Customers")  
  
Dim customerRow As CustomerDataSet.CustomersRow  
For Each customerRow In customers.Customers  
  Console.WriteLine(customerRow.CustomerID)  
Next  
```  
  
```csharp  
CustomerDataSet customers = new CustomerDataSet();  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers;",  
  "Data Source=(local);Integrated " +  
  "Security=SSPI;Initial Catalog=Northwind");  
  
adapter.Fill(customers, "Customers");  
  
foreach(CustomerDataSet.CustomersRow customerRow in customers.Customers)  
  Console.WriteLine(customerRow.CustomerID);  
```  
  
 <span data-ttu-id="7fcdd-120">A continuación se muestra el esquema XML utilizado para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7fcdd-120">Following is the XML Schema used for the example.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7fcdd-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fcdd-121">See Also</span></span>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataSet>  
 [<span data-ttu-id="7fcdd-122">Objetos DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="7fcdd-122">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [<span data-ttu-id="7fcdd-123">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="7fcdd-123">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="7fcdd-124">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="7fcdd-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
