---
title: Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: d32b5cb86bc5a138f9a5f438629d8e231be4ba94
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151174"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="6efb7-102">Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="6efb7-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>
<span data-ttu-id="6efb7-103">Esta sección ofrece información general sobre cómo se crea el esquema relacional de un `DataSet` a partir del documento de esquema del lenguaje de definición de esquema XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="6efb7-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="6efb7-104">En general, `complexType` para cada elemento secundario de un elemento `DataSet`de esquema, se genera una tabla en el archivo .</span><span class="sxs-lookup"><span data-stu-id="6efb7-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="6efb7-105">La estructura de la tabla está determinada por la definición del tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="6efb7-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="6efb7-106">Las tablas `DataSet` se crean en los elementos de nivel superior del esquema.</span><span class="sxs-lookup"><span data-stu-id="6efb7-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="6efb7-107">Sin embargo, una tabla solo `complexType` se crea `complexType` para un `complexType` elemento de nivel superior `complexType` cuando el `DataTable` elemento `DataSet`está anidado dentro de otro elemento, en cuyo caso el elemento anidado se asigna a un archivo .</span><span class="sxs-lookup"><span data-stu-id="6efb7-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="6efb7-108">Para obtener más información sobre el XSD, vea el World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), el XML Schema Part [1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/)y el XML Schema Part [2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span><span class="sxs-lookup"><span data-stu-id="6efb7-108">For more information about the XSD, see the World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), the [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/), and the [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span></span>  
  
 <span data-ttu-id="6efb7-109">En el ejemplo siguiente se `customers` muestra un esquema `MyDataSet` XML donde es el elemento secundario del elemento, que es un **DataSet** elemento.</span><span class="sxs-lookup"><span data-stu-id="6efb7-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
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
  
 <span data-ttu-id="6efb7-110">En el ejemplo anterior, `customers` es un elemento de tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="6efb7-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="6efb7-111">Por tanto, se analiza la definición del tipo complejo y el proceso de asignación crea la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6efb7-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="6efb7-112">El tipo de datos de cada columna de la tabla se deriva del tipo de esquema XML del correspondiente elemento o atributo especificado.</span><span class="sxs-lookup"><span data-stu-id="6efb7-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6efb7-113">Si el `customers` elemento es de un tipo de datos de esquema XML simple como **entero**, no se genera ninguna tabla.</span><span class="sxs-lookup"><span data-stu-id="6efb7-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="6efb7-114">Solo se crean tablas para elementos de nivel superior que sean de tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="6efb7-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="6efb7-115">En el esquema XML siguiente, el elemento `InStateCustomers` `OutOfStateCustomers` **Schema** tiene dos elementos secundarios y .</span><span class="sxs-lookup"><span data-stu-id="6efb7-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
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
  
 <span data-ttu-id="6efb7-116">Los dos elementos secundarios `InStateCustomers` y `OutOfStateCustomers` son elementos de tipo complejo (`customerType`).</span><span class="sxs-lookup"><span data-stu-id="6efb7-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="6efb7-117">Por lo tanto, el proceso de `DataSet`asignación genera las dos tablas idénticas siguientes en el archivo .</span><span class="sxs-lookup"><span data-stu-id="6efb7-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="6efb7-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6efb7-118">In This Section</span></span>  
 [<span data-ttu-id="6efb7-119">Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="6efb7-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="6efb7-120">Describe los elementos de esquema XML utilizados para `DataSet`crear restricciones de clave únicas y externas en un archivo .</span><span class="sxs-lookup"><span data-stu-id="6efb7-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="6efb7-121">Generación de relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="6efb7-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="6efb7-122">Describe los elementos de esquema XML utilizados `DataSet`para crear relaciones entre columnas de tabla en un archivo .</span><span class="sxs-lookup"><span data-stu-id="6efb7-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="6efb7-123">Restricciones y relaciones del esquema XML</span><span class="sxs-lookup"><span data-stu-id="6efb7-123">XML Schema Constraints and Relationships</span></span>](xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="6efb7-124">Describe cómo se crean las relaciones implícitamente cuando se `DataSet`utilizan elementos de esquema XML para crear restricciones en un archivo .</span><span class="sxs-lookup"><span data-stu-id="6efb7-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6efb7-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="6efb7-125">Related Sections</span></span>  
 [<span data-ttu-id="6efb7-126">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="6efb7-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="6efb7-127">Describe cómo cargar y conservar la estructura `DataSet` relacional y los datos en datos como XML.</span><span class="sxs-lookup"><span data-stu-id="6efb7-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6efb7-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6efb7-128">See also</span></span>

- [<span data-ttu-id="6efb7-129">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6efb7-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
