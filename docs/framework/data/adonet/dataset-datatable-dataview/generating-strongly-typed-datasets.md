---
description: Más información acerca de cómo generar conjuntos de DataSet fuertemente tipados
title: Generar conjuntos de datos fuertemente tipados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: c69aecc5a0a541c868dac3037c9dd0dbc3fe8383
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652437"
---
# <a name="generating-strongly-typed-datasets"></a><span data-ttu-id="552d4-103">Generar conjuntos de datos fuertemente tipados</span><span class="sxs-lookup"><span data-stu-id="552d4-103">Generating Strongly Typed DataSets</span></span>

<span data-ttu-id="552d4-104">Dado un esquema XML que cumple con el estándar del lenguaje de definición de esquemas XML (XSD), puede generar un fuertemente tipado <xref:System.Data.DataSet> mediante la herramienta XSD.exe que se proporciona con el kit de desarrollo de software (SDK) de Windows.</span><span class="sxs-lookup"><span data-stu-id="552d4-104">Given an XML Schema that complies with the XML Schema definition language (XSD) standard, you can generate a strongly typed <xref:System.Data.DataSet> using the XSD.exe tool provided with the Windows Software Development Kit (SDK).</span></span>  
  
 <span data-ttu-id="552d4-105">(Para crear un XSD a partir de tablas de base de datos, vea <xref:System.Data.DataSet.WriteXmlSchema%2A> o [trabajar con conjuntos de datos en Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio)).</span><span class="sxs-lookup"><span data-stu-id="552d4-105">(To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio)).</span></span>  
  
 <span data-ttu-id="552d4-106">En el código siguiente se muestra la sintaxis para generar un **conjunto** de elementos mediante esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="552d4-106">The following code shows the syntax for generating a **DataSet** using this tool.</span></span>  
  
```console  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 <span data-ttu-id="552d4-107">En esta sintaxis, la `/d` Directiva indica a la herramienta que genere un **DataSet** y `/l:` indica a la herramienta qué lenguaje usar (por ejemplo, C# o Visual Basic .net).</span><span class="sxs-lookup"><span data-stu-id="552d4-107">In this syntax, the `/d` directive tells the tool to generate a **DataSet**, and the `/l:` tells the tool what language to use (for example, C# or Visual Basic .NET).</span></span> <span data-ttu-id="552d4-108">La `/eld` Directiva opcional Especifica que puede utilizar LINQ to DataSet para realizar consultas en el **conjunto de DataSet generado.**</span><span class="sxs-lookup"><span data-stu-id="552d4-108">The optional `/eld` directive specifies that you can use LINQ to DataSet to query against the generated **DataSet.**</span></span> <span data-ttu-id="552d4-109">Esta opción se utiliza cuando también se especifica la opción `/d`.</span><span class="sxs-lookup"><span data-stu-id="552d4-109">This option is used when the `/d` option is also specified.</span></span> <span data-ttu-id="552d4-110">Para obtener más información, vea [consultar conjuntos de datos con tipo](../querying-typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="552d4-110">For more information, see [Querying Typed DataSets](../querying-typed-datasets.md).</span></span> <span data-ttu-id="552d4-111">La `/n:` Directiva opcional indica a la herramienta que también genere un espacio de nombres para el **DataSet** llamado **XSDSchema. Namespace**.</span><span class="sxs-lookup"><span data-stu-id="552d4-111">The optional `/n:` directive tells the tool to also generate a namespace for the **DataSet** called **XSDSchema.Namespace**.</span></span> <span data-ttu-id="552d4-112">El resultado del comando es XSDSchemaFileName.cs, que se puede compilar y utilizar en una aplicación de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="552d4-112">The output of the command is XSDSchemaFileName.cs, which can be compiled and used in an ADO.NET application.</span></span> <span data-ttu-id="552d4-113">El código generado puede compilarse como una biblioteca o un módulo.</span><span class="sxs-lookup"><span data-stu-id="552d4-113">The generated code can be compiled as a library or a module.</span></span>  
  
 <span data-ttu-id="552d4-114">En el siguiente código se muestra la sintaxis para compilar el código generado como una biblioteca mediante el compilador de C# (csc.exe).</span><span class="sxs-lookup"><span data-stu-id="552d4-114">The following code shows the syntax for compiling the generated code as a library using the C# compiler (csc.exe).</span></span>  
  
```console  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 <span data-ttu-id="552d4-115">La directiva `/t:` indica a la herramienta que compile en una biblioteca mientras que las directivas `/r:` especifican bibliotecas dependientes necesarias para la compilación.</span><span class="sxs-lookup"><span data-stu-id="552d4-115">The `/t:` directive tells the tool to compile to a library, and the `/r:` directives specify dependent libraries required to compile.</span></span> <span data-ttu-id="552d4-116">El resultado del comando es XSDSchemaFileName.dll, que se puede pasar al compilador al compilar una aplicación de ADO.NET con la directiva `/r:`.</span><span class="sxs-lookup"><span data-stu-id="552d4-116">The output of the command is XSDSchemaFileName.dll, which can be passed to the compiler when compiling an ADO.NET application with the `/r:` directive.</span></span>  
  
 <span data-ttu-id="552d4-117">En el siguiente código se muestra la sintaxis para tener acceso al espacio de nombres pasado a XSD.exe en una aplicación de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="552d4-117">The following code shows the syntax for accessing the namespace passed to XSD.exe in an ADO.NET application.</span></span>  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 <span data-ttu-id="552d4-118">En el ejemplo de código siguiente se utiliza un **conjunto** de datos con tipo denominado **CustomerDataSet** para cargar una lista de clientes de la base de datos **Northwind** .</span><span class="sxs-lookup"><span data-stu-id="552d4-118">The following code example uses a typed **DataSet** named **CustomerDataSet** to load a list of customers from the **Northwind** database.</span></span> <span data-ttu-id="552d4-119">Una vez que los datos se cargan con el método **Fill** , el ejemplo recorre en bucle cada cliente de la tabla **Customers** utilizando el objeto **CustomersRow** (**DataRow**) con tipo.</span><span class="sxs-lookup"><span data-stu-id="552d4-119">Once the data is loaded using the **Fill** method, the example loops through each customer in the **Customers** table using the typed **CustomersRow** (**DataRow**) object.</span></span> <span data-ttu-id="552d4-120">Esto proporciona acceso directo a la columna **CustomerID** , en lugar de a través de **DataColumnCollection**.</span><span class="sxs-lookup"><span data-stu-id="552d4-120">This provides direct access to the **CustomerID** column, as opposed to through the **DataColumnCollection**.</span></span>  
  
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
  
 <span data-ttu-id="552d4-121">El siguiente es el esquema XML que se usa para el ejemplo:</span><span class="sxs-lookup"><span data-stu-id="552d4-121">The following is the XML Schema used for the example:</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="552d4-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="552d4-122">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [<span data-ttu-id="552d4-123">Objetos DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="552d4-123">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="552d4-124">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="552d4-124">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="552d4-125">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="552d4-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
