---
title: Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3fcedf488a038f379bae26fd7da0f4bf027b2e55
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="ddeee-102">Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="ddeee-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>
<span data-ttu-id="ddeee-103">Esta sección ofrece información general sobre cómo se crea el esquema relacional de un `DataSet` a partir del documento de esquema del lenguaje de definición de esquema XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="ddeee-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="ddeee-104">En general, para cada `complexType` elemento secundario de un elemento de esquema, se genera una tabla en la `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="ddeee-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="ddeee-105">La estructura de la tabla está determinada por la definición del tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="ddeee-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="ddeee-106">Se crean tablas en el `DataSet` para elementos de nivel superior en el esquema.</span><span class="sxs-lookup"><span data-stu-id="ddeee-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="ddeee-107">Sin embargo, solo se crea una tabla para un nivel superior `complexType` elemento cuando el `complexType` elemento está anidado dentro de otro `complexType` elemento, en el que caso anidado `complexType` elemento se asigna a un `DataTable` dentro de la `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="ddeee-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="ddeee-108">Para obtener más información sobre el XSD, vea World Wide Web Consortium (W3C) XML Schema Part 0: Primer Recommendation, XML Schema Part 1: recomendación de estructuras y XML Schema Part 2: Datatypes Recommendation, ubicado en [http:// www.w3.org/](http://www.w3.org/TR/).</span><span class="sxs-lookup"><span data-stu-id="ddeee-108">For more information about the XSD, see the World Wide Web Consortium (W3C) XML Schema Part 0: Primer Recommendation, the XML Schema Part 1: Structures Recommendation, and the XML Schema Part 2: Datatypes Recommendation, located at [http://www.w3.org/](http://www.w3.org/TR/).</span></span>  
  
 <span data-ttu-id="ddeee-109">En el ejemplo siguiente se muestra un esquema XML donde `customers` es el elemento secundario de la `MyDataSet` elemento, que es un **conjunto de datos** elemento.</span><span class="sxs-lookup"><span data-stu-id="ddeee-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >   
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"   
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"   
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="ddeee-110">En el ejemplo anterior, `customers` es un elemento de tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="ddeee-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="ddeee-111">Por tanto, se analiza la definición del tipo complejo y el proceso de asignación crea la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ddeee-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 <span data-ttu-id="ddeee-112">El tipo de datos de cada columna de la tabla se deriva del tipo de esquema XML del correspondiente elemento o atributo especificado.</span><span class="sxs-lookup"><span data-stu-id="ddeee-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ddeee-113">Si el elemento `customers` es de un tipo de datos simple de esquema XML como **entero**, se generará ninguna tabla.</span><span class="sxs-lookup"><span data-stu-id="ddeee-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="ddeee-114">Solo se crean tablas para elementos de nivel superior que sean de tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="ddeee-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="ddeee-115">En el siguiente esquema XML, el **esquema** elemento tiene dos elementos secundarios, `InStateCustomers` y `OutOfStateCustomers`.</span><span class="sxs-lookup"><span data-stu-id="ddeee-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="ddeee-116">Los dos elementos secundarios `InStateCustomers` y `OutOfStateCustomers` son elementos de tipo complejo (`customerType`).</span><span class="sxs-lookup"><span data-stu-id="ddeee-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="ddeee-117">Por lo tanto, el proceso de asignación genera las dos siguientes tablas idénticas en el `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="ddeee-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="ddeee-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ddeee-118">In This Section</span></span>  
 [<span data-ttu-id="ddeee-119">Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="ddeee-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="ddeee-120">Describe los elementos de esquema XML utilizados para crear restricciones de clave únicas y externas en un `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="ddeee-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="ddeee-121">Generación de relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="ddeee-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="ddeee-122">Describe los elementos de esquema XML utilizados para crear relaciones entre columnas de tabla en un `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="ddeee-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="ddeee-123">Restricciones y relaciones del esquema XML</span><span class="sxs-lookup"><span data-stu-id="ddeee-123">XML Schema Constraints and Relationships</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="ddeee-124">Describe cómo se crean implícitamente relaciones cuando se utilizan elementos de esquema XML para crear restricciones en un `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="ddeee-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ddeee-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="ddeee-125">Related Sections</span></span>  
 [<span data-ttu-id="ddeee-126">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="ddeee-126">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="ddeee-127">Describe cómo cargar y hacer persistentes la estructura relacional y los datos en un `DataSet` como datos XML.</span><span class="sxs-lookup"><span data-stu-id="ddeee-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddeee-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddeee-128">See Also</span></span>  
 [<span data-ttu-id="ddeee-129">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="ddeee-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
