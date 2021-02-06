---
description: Obtener más información acerca de cómo derivar una estructura relacional de conjunto de objetos a partir de un esquema XML (XSD)
title: Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: c2d2dc8ab9c8a1cf77c79fbde38a06de6f120c82
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652528"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="f8a7d-103">Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="f8a7d-103">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>

<span data-ttu-id="f8a7d-104">Esta sección ofrece información general sobre cómo se crea el esquema relacional de un `DataSet` a partir del documento de esquema del lenguaje de definición de esquema XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="f8a7d-104">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="f8a7d-105">En general, para cada `complexType` elemento secundario de un elemento de esquema, se genera una tabla en `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="f8a7d-105">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="f8a7d-106">La estructura de la tabla está determinada por la definición del tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="f8a7d-106">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="f8a7d-107">Las tablas se crean en `DataSet` para los elementos de nivel superior del esquema.</span><span class="sxs-lookup"><span data-stu-id="f8a7d-107">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="f8a7d-108">Sin embargo, solo se crea una tabla para un elemento de nivel superior `complexType` cuando el `complexType` elemento está anidado dentro `complexType` de otro elemento, en cuyo caso el `complexType` elemento anidado se asigna a un `DataTable` dentro de `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="f8a7d-108">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="f8a7d-109">Para obtener más información acerca de XSD, vea el esquema XML de World Wide Web Consortium (W3C) [parte 0: recomendación básica](https://www.w3.org/TR/xmlschema-0/), el [esquema XML parte 1: recomendación de estructuras](https://www.w3.org/TR/xmlschema-1/)y la [recomendación del esquema XML parte 2: tipos de datos](https://www.w3.org/TR/xmlschema-2/).</span><span class="sxs-lookup"><span data-stu-id="f8a7d-109">For more information about the XSD, see the World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), the [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/), and the [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span></span>  
  
 <span data-ttu-id="f8a7d-110">En el ejemplo siguiente se muestra un esquema XML donde `customers` es el elemento secundario del `MyDataSet` elemento, que es un elemento **DataSet** .</span><span class="sxs-lookup"><span data-stu-id="f8a7d-110">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
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
  
 <span data-ttu-id="f8a7d-111">En el ejemplo anterior, `customers` es un elemento de tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="f8a7d-111">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="f8a7d-112">Por tanto, se analiza la definición del tipo complejo y el proceso de asignación crea la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f8a7d-112">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="f8a7d-113">El tipo de datos de cada columna de la tabla se deriva del tipo de esquema XML del correspondiente elemento o atributo especificado.</span><span class="sxs-lookup"><span data-stu-id="f8a7d-113">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8a7d-114">Si el elemento `customers` es de un tipo de datos de esquema XML simple como **Integer**, no se genera ninguna tabla.</span><span class="sxs-lookup"><span data-stu-id="f8a7d-114">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="f8a7d-115">Solo se crean tablas para elementos de nivel superior que sean de tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="f8a7d-115">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="f8a7d-116">En el siguiente esquema XML, el elemento **Schema** tiene dos elementos secundarios, `InStateCustomers` y `OutOfStateCustomers` .</span><span class="sxs-lookup"><span data-stu-id="f8a7d-116">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
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
  
 <span data-ttu-id="f8a7d-117">Los dos elementos secundarios `InStateCustomers` y `OutOfStateCustomers` son elementos de tipo complejo (`customerType`).</span><span class="sxs-lookup"><span data-stu-id="f8a7d-117">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="f8a7d-118">Por lo tanto, el proceso de asignación genera las dos siguientes tablas idénticas en `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="f8a7d-118">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="f8a7d-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f8a7d-119">In This Section</span></span>  

 [<span data-ttu-id="f8a7d-120">Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="f8a7d-120">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="f8a7d-121">Describe los elementos de esquema XML utilizados para crear restricciones de clave única y externa en `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="f8a7d-121">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="f8a7d-122">Generar relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="f8a7d-122">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="f8a7d-123">Describe los elementos de esquema XML utilizados para crear relaciones entre las columnas de la tabla en un `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="f8a7d-123">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="f8a7d-124">Restricciones y relaciones del esquema XML</span><span class="sxs-lookup"><span data-stu-id="f8a7d-124">XML Schema Constraints and Relationships</span></span>](xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="f8a7d-125">Describe cómo se crean implícitamente las relaciones al utilizar elementos de esquema XML para crear restricciones en un `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="f8a7d-125">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f8a7d-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="f8a7d-126">Related Sections</span></span>  

 [<span data-ttu-id="f8a7d-127">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="f8a7d-127">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="f8a7d-128">Describe cómo cargar y conservar la estructura relacional y los datos de `DataSet` como datos XML.</span><span class="sxs-lookup"><span data-stu-id="f8a7d-128">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8a7d-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8a7d-129">See also</span></span>

- [<span data-ttu-id="f8a7d-130">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f8a7d-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
