---
title: Generar conjuntos de datos fuertemente tipados
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 867c6f5fa918b0886d8d618e89c62201cd92b213
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="generating-strongly-typed-datasets"></a><span data-ttu-id="39041-102">Generar conjuntos de datos fuertemente tipados</span><span class="sxs-lookup"><span data-stu-id="39041-102">Generating Strongly Typed DataSets</span></span>
<span data-ttu-id="39041-103">A partir de un esquema XML que cumple con el estándar del lenguaje de definición de esquemas XML (XSD), es posible generar un objeto <xref:System.Data.DataSet> fuertemente tipado mediante la herramienta XSD.exe incluida en [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39041-103">Given an XML Schema that complies with the XML Schema definition language (XSD) standard, you can generate a strongly typed <xref:System.Data.DataSet> using the XSD.exe tool provided with the [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)].</span></span>  
  
 <span data-ttu-id="39041-104">(Para crear un xsd a partir de tablas de base de datos, vea <xref:System.Data.DataSet.WriteXmlSchema%2A> o [trabajar con conjuntos de datos en Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)).</span><span class="sxs-lookup"><span data-stu-id="39041-104">(To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)).</span></span>  
  
 <span data-ttu-id="39041-105">El código siguiente muestra la sintaxis para generar un **conjunto de datos** con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="39041-105">The following code shows the syntax for generating a **DataSet** using this tool.</span></span>  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 <span data-ttu-id="39041-106">En esta sintaxis, la `/d` directiva indica a la herramienta que genere un **conjunto de datos**y el `/l:` indica a la herramienta lenguaje que debe utilizar (por ejemplo, C# o Visual Basic. NET).</span><span class="sxs-lookup"><span data-stu-id="39041-106">In this syntax, the `/d` directive tells the tool to generate a **DataSet**, and the `/l:` tells the tool what language to use (for example, C# or Visual Basic .NET).</span></span> <span data-ttu-id="39041-107">Opcional `/eld` directiva especifica que se puede utilizar [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] consultas en los botones generados **conjunto de datos.**</span><span class="sxs-lookup"><span data-stu-id="39041-107">The optional `/eld` directive specifies that you can use [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] to query against the generated **DataSet.**</span></span> <span data-ttu-id="39041-108">Esta opción se utiliza cuando también se especifica la opción `/d`.</span><span class="sxs-lookup"><span data-stu-id="39041-108">This option is used when the `/d` option is also specified.</span></span> <span data-ttu-id="39041-109">Para obtener más información, consulte [consultar conjuntos de datos con tipo](../../../../../docs/framework/data/adonet/querying-typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="39041-109">For more information, see [Querying Typed DataSets](../../../../../docs/framework/data/adonet/querying-typed-datasets.md).</span></span> <span data-ttu-id="39041-110">Opcional `/n:` directiva indica a la herramienta que genere también un espacio de nombres para el **conjunto de datos** llama **XSDSchema.Namespace**.</span><span class="sxs-lookup"><span data-stu-id="39041-110">The optional `/n:` directive tells the tool to also generate a namespace for the **DataSet** called **XSDSchema.Namespace**.</span></span> <span data-ttu-id="39041-111">El resultado del comando es XSDSchemaFileName.cs, que se puede compilar y utilizar en una aplicación de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="39041-111">The output of the command is XSDSchemaFileName.cs, which can be compiled and used in an ADO.NET application.</span></span> <span data-ttu-id="39041-112">El código generado puede compilarse como una biblioteca o un módulo.</span><span class="sxs-lookup"><span data-stu-id="39041-112">The generated code can be compiled as a library or a module.</span></span>  
  
 <span data-ttu-id="39041-113">En el siguiente código se muestra la sintaxis para compilar el código generado como una biblioteca mediante el compilador de C# (csc.exe).</span><span class="sxs-lookup"><span data-stu-id="39041-113">The following code shows the syntax for compiling the generated code as a library using the C# compiler (csc.exe).</span></span>  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 <span data-ttu-id="39041-114">La directiva `/t:` indica a la herramienta que compile en una biblioteca mientras que las directivas `/r:` especifican bibliotecas dependientes necesarias para la compilación.</span><span class="sxs-lookup"><span data-stu-id="39041-114">The `/t:` directive tells the tool to compile to a library, and the `/r:` directives specify dependent libraries required to compile.</span></span> <span data-ttu-id="39041-115">El resultado del comando es XSDSchemaFileName.dll, que se puede pasar al compilador al compilar una aplicación de ADO.NET con la directiva `/r:`.</span><span class="sxs-lookup"><span data-stu-id="39041-115">The output of the command is XSDSchemaFileName.dll, which can be passed to the compiler when compiling an ADO.NET application with the `/r:` directive.</span></span>  
  
 <span data-ttu-id="39041-116">En el siguiente código se muestra la sintaxis para tener acceso al espacio de nombres pasado a XSD.exe en una aplicación de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="39041-116">The following code shows the syntax for accessing the namespace passed to XSD.exe in an ADO.NET application.</span></span>  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 <span data-ttu-id="39041-117">En el ejemplo de código siguiente se utiliza un **conjunto de datos** denominado **CustomerDataSet** para cargar una lista de los clientes de la **Northwind** base de datos.</span><span class="sxs-lookup"><span data-stu-id="39041-117">The following code example uses a typed **DataSet** named **CustomerDataSet** to load a list of customers from the **Northwind** database.</span></span> <span data-ttu-id="39041-118">Una vez que los datos se cargan con la **rellenar** método, el ejemplo recorre cada cliente de la **clientes** con el tipo de tabla **CustomersRow** ( **DataRow**) objeto.</span><span class="sxs-lookup"><span data-stu-id="39041-118">Once the data is loaded using the **Fill** method, the example loops through each customer in the **Customers** table using the typed **CustomersRow** (**DataRow**) object.</span></span> <span data-ttu-id="39041-119">Esto proporciona acceso directo a la **CustomerID** columna, en lugar de a través del **DataColumnCollection**.</span><span class="sxs-lookup"><span data-stu-id="39041-119">This provides direct access to the **CustomerID** column, as opposed to through the **DataColumnCollection**.</span></span>  
  
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
  
 <span data-ttu-id="39041-120">A continuación se muestra el esquema XML utilizado para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="39041-120">Following is the XML Schema used for the example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="39041-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="39041-121">See Also</span></span>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataSet>  
 [<span data-ttu-id="39041-122">Objetos DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="39041-122">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [<span data-ttu-id="39041-123">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="39041-123">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="39041-124">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="39041-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
