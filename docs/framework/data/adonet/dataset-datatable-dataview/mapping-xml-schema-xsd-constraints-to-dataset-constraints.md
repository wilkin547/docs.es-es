---
title: Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
ms.openlocfilehash: a2b28b0dcb2e2858c7328854650667f51e83166a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185293"
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="66132-102">Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="66132-102">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>

<span data-ttu-id="66132-103">El lenguaje de definición de esquemas XML (XSD) permite especificar restricciones para los elementos y atributos que define.</span><span class="sxs-lookup"><span data-stu-id="66132-103">The XML Schema definition language (XSD) allows constraints to be specified on the elements and attributes it defines.</span></span> <span data-ttu-id="66132-104">Al asignar un esquema XML a un esquema relacional en un <xref:System.Data.DataSet> , las restricciones de esquema XML se asignan a las restricciones relacionales apropiadas en las tablas y columnas del **conjunto de DataSet**.</span><span class="sxs-lookup"><span data-stu-id="66132-104">When mapping an XML Schema to relational schema in a <xref:System.Data.DataSet>, XML Schema constraints are mapped to appropriate relational constraints on the tables and columns within the **DataSet**.</span></span>  
  
 <span data-ttu-id="66132-105">En esta sección se describe la asignación de las siguientes restricciones de esquema XML:</span><span class="sxs-lookup"><span data-stu-id="66132-105">This section discusses the mapping of the following XML Schema constraints:</span></span>  
  
- <span data-ttu-id="66132-106">La restricción de unicidad especificada mediante el elemento **único** .</span><span class="sxs-lookup"><span data-stu-id="66132-106">The uniqueness constraint specified using the **unique** element.</span></span>  
  
- <span data-ttu-id="66132-107">Restricción de clave especificada mediante el elemento **key** .</span><span class="sxs-lookup"><span data-stu-id="66132-107">The key constraint specified using the **key** element.</span></span>  
  
- <span data-ttu-id="66132-108">La restricción keyref especificada mediante el elemento **keyref** .</span><span class="sxs-lookup"><span data-stu-id="66132-108">The keyref constraint specified using the **keyref** element.</span></span>  
  
 <span data-ttu-id="66132-109">El uso de una restricción sobre un elemento o un atributo permite especificar ciertas restricciones para los valores del elemento en cualquier instancia del documento.</span><span class="sxs-lookup"><span data-stu-id="66132-109">By using a constraint on an element or attribute, you specify certain restrictions on the values of the element in any instance of the document.</span></span> <span data-ttu-id="66132-110">Por ejemplo, una restricción de clave en un elemento secundario **CustomerID** de un elemento **Customer** del esquema indica que los valores del elemento secundario **CustomerID** deben ser únicos en cualquier instancia de documento y que no se permiten valores NULL.</span><span class="sxs-lookup"><span data-stu-id="66132-110">For example, a key constraint on a **CustomerID** child element of a **Customer** element in the schema indicates that the values of the **CustomerID** child element must be unique in any document instance, and that null values are not allowed.</span></span>  
  
 <span data-ttu-id="66132-111">También se pueden especificar restricciones entre los elementos y atributos de un documento para establecer una relación dentro del documento.</span><span class="sxs-lookup"><span data-stu-id="66132-111">Constraints can also be specified between elements and attributes in a document, in order to establish a relationship within the document.</span></span> <span data-ttu-id="66132-112">Las restricciones key y keyref se utilizan en el esquema para especificar las restricciones dentro del documento, lo que da como resultado una relación entre los elementos y atributos del documento.</span><span class="sxs-lookup"><span data-stu-id="66132-112">The key and keyref constraints are used in the schema to specify the constraints within the document, resulting in a relationship between document elements and attributes.</span></span>  
  
 <span data-ttu-id="66132-113">El proceso de asignación convierte estas restricciones de esquema en restricciones adecuadas en las tablas creadas en el **conjunto de DataSet**.</span><span class="sxs-lookup"><span data-stu-id="66132-113">The mapping process converts these schema constraints into appropriate constraints on the tables created within the **DataSet**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="66132-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="66132-114">In This Section</span></span>  

 [<span data-ttu-id="66132-115">Asignar restricciones UNIQUE de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="66132-115">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>](map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="66132-116">Describe los elementos de esquema XML utilizados para crear restricciones UNIQUE en un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="66132-116">Describes the XML Schema elements used to create unique constraints in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="66132-117">Asignar restricciones KEY de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="66132-117">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>](map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="66132-118">Describe los elementos de esquema XML utilizados para crear restricciones de clave (restricciones únicas en las que no se permiten valores NULL) en un **conjunto de DataSet**.</span><span class="sxs-lookup"><span data-stu-id="66132-118">Describes the XML Schema elements used to create key constraints (unique constraints where null values are not allowed) in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="66132-119">Asignar restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="66132-119">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>](map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="66132-120">Describe los elementos de esquema XML utilizados para crear restricciones keyref (clave externa) en un **conjunto de DataSet**.</span><span class="sxs-lookup"><span data-stu-id="66132-120">Describes the XML Schema elements used to create keyref (foreign key) constraints in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="66132-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="66132-121">Related Sections</span></span>  

 [<span data-ttu-id="66132-122">Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="66132-122">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="66132-123">Describe la estructura relacional, o esquema, de un **DataSet** que se crea a partir del esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="66132-123">Describes the relational structure, or schema, of a **DataSet** that is created from XSD schema.</span></span>  
  
 [<span data-ttu-id="66132-124">Generar relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="66132-124">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="66132-125">Describe los elementos de esquema XML que se utilizan para crear relaciones entre las columnas de tabla de un **conjunto de DataSet**.</span><span class="sxs-lookup"><span data-stu-id="66132-125">Describes the XML Schema elements used to create relations between table columns in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66132-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66132-126">See also</span></span>

- [<span data-ttu-id="66132-127">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="66132-127">ADO.NET Overview</span></span>](../ado-net-overview.md)
