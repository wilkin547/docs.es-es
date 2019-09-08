---
title: Generar conjuntos de datos fuertemente tipados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: f1c1fd77bed700fae8e5a658da8b267120518ca9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786308"
---
# <a name="generating-strongly-typed-datasets"></a><span data-ttu-id="302ad-102">Generar conjuntos de datos fuertemente tipados</span><span class="sxs-lookup"><span data-stu-id="302ad-102">Generating Strongly Typed DataSets</span></span>
<span data-ttu-id="302ad-103">Dado un esquema XML que cumple con el estándar del lenguaje de definición de esquemas XML (XSD), puede generar un fuertemente <xref:System.Data.DataSet> tipado mediante la herramienta xsd. exe proporcionada con el kit de desarrollo de software (SDK) de Windows.</span><span class="sxs-lookup"><span data-stu-id="302ad-103">Given an XML Schema that complies with the XML Schema definition language (XSD) standard, you can generate a strongly typed <xref:System.Data.DataSet> using the XSD.exe tool provided with the Windows Software Development Kit (SDK).</span></span>  
  
 <span data-ttu-id="302ad-104">(Para crear un XSD a partir de tablas de <xref:System.Data.DataSet.WriteXmlSchema%2A> base de datos, vea o [trabajar con conjuntos de datos en Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio)).</span><span class="sxs-lookup"><span data-stu-id="302ad-104">(To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio)).</span></span>  
  
 <span data-ttu-id="302ad-105">En el código siguiente se muestra la sintaxis para generar un **conjunto** de elementos mediante esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="302ad-105">The following code shows the syntax for generating a **DataSet** using this tool.</span></span>  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 <span data-ttu-id="302ad-106">En esta sintaxis, la `/d` Directiva indica a la herramienta que genere un **DataSet**y `/l:` indica a la herramienta qué lenguaje usar (por ejemplo, C# o Visual Basic .net).</span><span class="sxs-lookup"><span data-stu-id="302ad-106">In this syntax, the `/d` directive tells the tool to generate a **DataSet**, and the `/l:` tells the tool what language to use (for example, C# or Visual Basic .NET).</span></span> <span data-ttu-id="302ad-107">La directiva `/eld` opcional Especifica que puede utilizar LINQ to DataSet para realizar consultas en el **conjunto de DataSet generado.**</span><span class="sxs-lookup"><span data-stu-id="302ad-107">The optional `/eld` directive specifies that you can use LINQ to DataSet to query against the generated **DataSet.**</span></span> <span data-ttu-id="302ad-108">Esta opción se utiliza cuando también se especifica la opción `/d`.</span><span class="sxs-lookup"><span data-stu-id="302ad-108">This option is used when the `/d` option is also specified.</span></span> <span data-ttu-id="302ad-109">Para obtener más información, vea [consultar conjuntos de datos con tipo](../querying-typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="302ad-109">For more information, see [Querying Typed DataSets](../querying-typed-datasets.md).</span></span> <span data-ttu-id="302ad-110">La directiva `/n:` opcional indica a la herramienta que también genere un espacio de nombres para el **DataSet** llamado **XSDSchema. Namespace**.</span><span class="sxs-lookup"><span data-stu-id="302ad-110">The optional `/n:` directive tells the tool to also generate a namespace for the **DataSet** called **XSDSchema.Namespace**.</span></span> <span data-ttu-id="302ad-111">El resultado del comando es XSDSchemaFileName.cs, que se puede compilar y utilizar en una aplicación de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="302ad-111">The output of the command is XSDSchemaFileName.cs, which can be compiled and used in an ADO.NET application.</span></span> <span data-ttu-id="302ad-112">El código generado puede compilarse como una biblioteca o un módulo.</span><span class="sxs-lookup"><span data-stu-id="302ad-112">The generated code can be compiled as a library or a module.</span></span>  
  
 <span data-ttu-id="302ad-113">En el siguiente código se muestra la sintaxis para compilar el código generado como una biblioteca mediante el compilador de C# (csc.exe).</span><span class="sxs-lookup"><span data-stu-id="302ad-113">The following code shows the syntax for compiling the generated code as a library using the C# compiler (csc.exe).</span></span>  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 <span data-ttu-id="302ad-114">La directiva `/t:` indica a la herramienta que compile en una biblioteca mientras que las directivas `/r:` especifican bibliotecas dependientes necesarias para la compilación.</span><span class="sxs-lookup"><span data-stu-id="302ad-114">The `/t:` directive tells the tool to compile to a library, and the `/r:` directives specify dependent libraries required to compile.</span></span> <span data-ttu-id="302ad-115">El resultado del comando es XSDSchemaFileName.dll, que se puede pasar al compilador al compilar una aplicación de ADO.NET con la directiva `/r:`.</span><span class="sxs-lookup"><span data-stu-id="302ad-115">The output of the command is XSDSchemaFileName.dll, which can be passed to the compiler when compiling an ADO.NET application with the `/r:` directive.</span></span>  
  
 <span data-ttu-id="302ad-116">En el siguiente código se muestra la sintaxis para tener acceso al espacio de nombres pasado a XSD.exe en una aplicación de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="302ad-116">The following code shows the syntax for accessing the namespace passed to XSD.exe in an ADO.NET application.</span></span>  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 <span data-ttu-id="302ad-117">En el ejemplo de código siguiente se utiliza un **conjunto** de datos con tipo denominado **CustomerDataSet** para cargar una lista de clientes de la base de datos **Northwind** .</span><span class="sxs-lookup"><span data-stu-id="302ad-117">The following code example uses a typed **DataSet** named **CustomerDataSet** to load a list of customers from the **Northwind** database.</span></span> <span data-ttu-id="302ad-118">Una vez que los datos se cargan con el método **Fill** , el ejemplo recorre en bucle cada cliente de la tabla **Customers** utilizando el objeto **CustomersRow** (**DataRow**) con tipo.</span><span class="sxs-lookup"><span data-stu-id="302ad-118">Once the data is loaded using the **Fill** method, the example loops through each customer in the **Customers** table using the typed **CustomersRow** (**DataRow**) object.</span></span> <span data-ttu-id="302ad-119">Esto proporciona acceso directo a la columna **CustomerID** , en lugar de a través de **DataColumnCollection**.</span><span class="sxs-lookup"><span data-stu-id="302ad-119">This provides direct access to the **CustomerID** column, as opposed to through the **DataColumnCollection**.</span></span>  
  
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
  
 <span data-ttu-id="302ad-120">A continuación se muestra el esquema XML utilizado para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="302ad-120">Following is the XML Schema used for the example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="302ad-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="302ad-121">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [<span data-ttu-id="302ad-122">Objetos DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="302ad-122">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="302ad-123">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="302ad-123">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="302ad-124">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="302ad-124">ADO.NET Overview</span></span>](../ado-net-overview.md)
