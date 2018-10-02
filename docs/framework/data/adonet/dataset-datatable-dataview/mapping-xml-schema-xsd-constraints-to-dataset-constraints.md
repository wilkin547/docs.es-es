---
title: Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
ms.openlocfilehash: c9cd97535a0165b82f0823c1f17f621491d4255c
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47862562"
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="4ace6-102">Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="4ace6-102">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="4ace6-103">El lenguaje de definición de esquemas XML (XSD) permite especificar restricciones para los elementos y atributos que define.</span><span class="sxs-lookup"><span data-stu-id="4ace6-103">The XML Schema definition language (XSD) allows constraints to be specified on the elements and attributes it defines.</span></span> <span data-ttu-id="4ace6-104">Al asignar un esquema XML al esquema relacional de un <xref:System.Data.DataSet>, restricciones de esquema XML se asignan a las restricciones relacionales apropiadas en las tablas y columnas dentro de la **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="4ace6-104">When mapping an XML Schema to relational schema in a <xref:System.Data.DataSet>, XML Schema constraints are mapped to appropriate relational constraints on the tables and columns within the **DataSet**.</span></span>  
  
 <span data-ttu-id="4ace6-105">En esta sección se describe la asignación de las siguientes restricciones de esquema XML:</span><span class="sxs-lookup"><span data-stu-id="4ace6-105">This section discusses the mapping of the following XML Schema constraints:</span></span>  
  
-   <span data-ttu-id="4ace6-106">La restricción de unicidad especificada mediante el **único** elemento.</span><span class="sxs-lookup"><span data-stu-id="4ace6-106">The uniqueness constraint specified using the **unique** element.</span></span>  
  
-   <span data-ttu-id="4ace6-107">La restricción de clave especificada mediante el **clave** elemento.</span><span class="sxs-lookup"><span data-stu-id="4ace6-107">The key constraint specified using the **key** element.</span></span>  
  
-   <span data-ttu-id="4ace6-108">La restricción keyref especificada mediante el **keyref** elemento.</span><span class="sxs-lookup"><span data-stu-id="4ace6-108">The keyref constraint specified using the **keyref** element.</span></span>  
  
 <span data-ttu-id="4ace6-109">El uso de una restricción sobre un elemento o un atributo permite especificar ciertas restricciones para los valores del elemento en cualquier instancia del documento.</span><span class="sxs-lookup"><span data-stu-id="4ace6-109">By using a constraint on an element or attribute, you specify certain restrictions on the values of the element in any instance of the document.</span></span> <span data-ttu-id="4ace6-110">Por ejemplo, una restricción de clave en un **CustomerID** elemento secundario de un **cliente** elemento en el esquema indica que los valores de la **CustomerID** debe ser el elemento secundario único en cualquier instancia del documento, y que no se permiten valores null.</span><span class="sxs-lookup"><span data-stu-id="4ace6-110">For example, a key constraint on a **CustomerID** child element of a **Customer** element in the schema indicates that the values of the **CustomerID** child element must be unique in any document instance, and that null values are not allowed.</span></span>  
  
 <span data-ttu-id="4ace6-111">También se pueden especificar restricciones entre los elementos y atributos de un documento para establecer una relación dentro del documento.</span><span class="sxs-lookup"><span data-stu-id="4ace6-111">Constraints can also be specified between elements and attributes in a document, in order to establish a relationship within the document.</span></span> <span data-ttu-id="4ace6-112">Las restricciones key y keyref se utilizan en el esquema para especificar las restricciones dentro del documento, lo que da como resultado una relación entre los elementos y atributos del documento.</span><span class="sxs-lookup"><span data-stu-id="4ace6-112">The key and keyref constraints are used in the schema to specify the constraints within the document, resulting in a relationship between document elements and attributes.</span></span>  
  
 <span data-ttu-id="4ace6-113">El proceso de asignación convierte estas restricciones del esquema en las restricciones apropiadas para las tablas creadas dentro de la **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="4ace6-113">The mapping process converts these schema constraints into appropriate constraints on the tables created within the **DataSet**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ace6-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4ace6-114">In This Section</span></span>  
 [<span data-ttu-id="4ace6-115">Asignación de restricciones UNIQUE de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="4ace6-115">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="4ace6-116">Describe los elementos de esquema XML utilizados para crear restricciones unique en una **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="4ace6-116">Describes the XML Schema elements used to create unique constraints in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="4ace6-117">Asignación de restricciones KEY de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="4ace6-117">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="4ace6-118">Describe los elementos de esquema XML utilizados para crear restricciones de clave (restricciones únicas donde no se permiten valores null) en un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="4ace6-118">Describes the XML Schema elements used to create key constraints (unique constraints where null values are not allowed) in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="4ace6-119">Asignación de restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="4ace6-119">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="4ace6-120">Describe los elementos de esquema XML utilizados para crear restricciones (clave externa) en keyref un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="4ace6-120">Describes the XML Schema elements used to create keyref (foreign key) constraints in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4ace6-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="4ace6-121">Related Sections</span></span>  
 [<span data-ttu-id="4ace6-122">Derivación de una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="4ace6-122">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="4ace6-123">Describe la estructura relacional, o esquema, de un **DataSet** creado a partir de un esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="4ace6-123">Describes the relational structure, or schema, of a **DataSet** that is created from XSD schema.</span></span>  
  
 [<span data-ttu-id="4ace6-124">Generación de relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="4ace6-124">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="4ace6-125">Describe los elementos de esquema XML utilizados para crear relaciones entre columnas de tabla en un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="4ace6-125">Describes the XML Schema elements used to create relations between table columns in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ace6-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ace6-126">See Also</span></span>  
 [<span data-ttu-id="4ace6-127">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="4ace6-127">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
