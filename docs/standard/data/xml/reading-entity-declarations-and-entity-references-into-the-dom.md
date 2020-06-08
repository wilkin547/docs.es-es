---
title: Leer declaraciones de entidad y referencias de entidad en DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 86dba977-5cc4-4567-964f-027ffabc47b2
ms.openlocfilehash: 41d88de9ee988a29c54c6e2c6c437963b9f79cf8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289881"
---
# <a name="reading-entity-declarations-and-entity-references-into-the-dom"></a><span data-ttu-id="5e36c-102">Leer declaraciones de entidad y referencias de entidad en DOM</span><span class="sxs-lookup"><span data-stu-id="5e36c-102">Reading Entity Declarations and Entity References into the DOM</span></span>
<span data-ttu-id="5e36c-103">Una entidad es una declaración que establece un nombre que se va a utilizar en el código XML en lugar de contenido o marcado.</span><span class="sxs-lookup"><span data-stu-id="5e36c-103">An entity is a declaration that states a name to be used in the XML in place of content or markup.</span></span> <span data-ttu-id="5e36c-104">Para las entidades hay dos partes.</span><span class="sxs-lookup"><span data-stu-id="5e36c-104">There are two parts to entities.</span></span> <span data-ttu-id="5e36c-105">En primer lugar, se debe asociar un nombre al contenido de reemplazo, utilizando una declaración de entidad.</span><span class="sxs-lookup"><span data-stu-id="5e36c-105">First, you must tie a name to the replacement content using an entity declaration.</span></span> <span data-ttu-id="5e36c-106">Una declaración de entidad se crea mediante la sintaxis `<!ENTITY name "value">` incluida o en una DTD o esquema XML.</span><span class="sxs-lookup"><span data-stu-id="5e36c-106">An entity declaration is created by using the `<!ENTITY name "value">` syntax in a document type definition (DTD) or XML schema.</span></span> <span data-ttu-id="5e36c-107">En segundo lugar, el nombre definido en la declaración de entidad se utiliza posteriormente en el XML.</span><span class="sxs-lookup"><span data-stu-id="5e36c-107">Secondly, the name defined in the entity declaration is subsequently used in the XML.</span></span> <span data-ttu-id="5e36c-108">Al utilizarlo en el código XML, se conoce como referencia de entidad.</span><span class="sxs-lookup"><span data-stu-id="5e36c-108">When used in the XML, it is called an entity reference.</span></span> <span data-ttu-id="5e36c-109">Por ejemplo, en la declaración de entidad siguiente se declara una entidad del nombre `publisher` que está asociada al contenido de "Microsoft Press".</span><span class="sxs-lookup"><span data-stu-id="5e36c-109">For example, the following entity declaration declares an entity of the name `publisher` being associated with the content of "Microsoft Press".</span></span>  
  
```xml  
<!ENTITY publisher "Microsoft Press">  
```  
  
 <span data-ttu-id="5e36c-110">En el ejemplo siguiente se muestra el uso de esta declaración de entidad en XML como una referencia de entidad.</span><span class="sxs-lookup"><span data-stu-id="5e36c-110">The following example shows the use of this entity declaration in XML as an entity reference.</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="5e36c-111">Algunos analizadores expanden las entidades automáticamente al cargar un documento en la memoria.</span><span class="sxs-lookup"><span data-stu-id="5e36c-111">Some parsers automatically expand entities when a document is loaded into memory.</span></span> <span data-ttu-id="5e36c-112">Por tanto, cuando se lee el XML en la memoria, se recuerdan y guardan las declaraciones de entidad.</span><span class="sxs-lookup"><span data-stu-id="5e36c-112">Therefore, when the XML is being read into memory, entity declarations are remembered and saved.</span></span> <span data-ttu-id="5e36c-113">Cuando el analizador encuentra posteriormente caracteres `&;`, que identifican una referencia de entidad general, el analizador busca dicho nombre en una tabla de declaraciones de entidad.</span><span class="sxs-lookup"><span data-stu-id="5e36c-113">When the parser subsequently encounters `&;` characters, which identify a general entity reference, the parser looks up that name in an entity declaration table.</span></span> <span data-ttu-id="5e36c-114">La referencia, `&publisher;`, se reemplaza por el contenido que representa.</span><span class="sxs-lookup"><span data-stu-id="5e36c-114">The reference, `&publisher;` is replaced by the content that it represents.</span></span> <span data-ttu-id="5e36c-115">Con el siguiente código XML,</span><span class="sxs-lookup"><span data-stu-id="5e36c-115">Using the following XML,</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="5e36c-116">que expande la referencia de entidad y se reemplaza `&publisher;` por el contenido de Microsoft Press, se proporciona el siguiente código XML expandido.</span><span class="sxs-lookup"><span data-stu-id="5e36c-116">expanding the entity reference and replacing the `&publisher;` with the Microsoft Press content gives the following expanded XML.</span></span>  
  
 <span data-ttu-id="5e36c-117">**Salida**</span><span class="sxs-lookup"><span data-stu-id="5e36c-117">**Output**</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by Microsoft Press</pubinfo>  
```  
  
 <span data-ttu-id="5e36c-118">Hay muchos tipos de entidades.</span><span class="sxs-lookup"><span data-stu-id="5e36c-118">There are many kinds of entities.</span></span> <span data-ttu-id="5e36c-119">En el diagrama siguiente se muestra la división de los tipos de entidades y terminología.</span><span class="sxs-lookup"><span data-stu-id="5e36c-119">The following diagram shows the breakdown of entity types and terminology.</span></span>  
  
 <span data-ttu-id="5e36c-120">![Diagrama de flujo de la jerarquía de tipos de entidad](media/entity-hierarchy.gif "Entity_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="5e36c-120">![flow chart of entity type hierarchy](media/entity-hierarchy.gif "Entity_hierarchy")</span></span>  
  
 <span data-ttu-id="5e36c-121">La forma predeterminada para la implementación Microsoft .NET Framework de Document Object Model (DOM) XML es preservar las referencias de entidades y no expandir las entidades cuando se carga XML.</span><span class="sxs-lookup"><span data-stu-id="5e36c-121">The default for the Microsoft .NET Framework implementation of the XML Document Object Model (DOM) is to preserve the entities references and not expand the entities when the XML is loaded.</span></span> <span data-ttu-id="5e36c-122">Esto implica que, al cargar un documento en DOM, se crea un nodo **XmlEntityReference** que contiene la variable de referencia `&publisher;` con nodos secundarios que representan el contenido de la entidad declarado en la DTD.</span><span class="sxs-lookup"><span data-stu-id="5e36c-122">The implication of this is that as a document is loaded in the DOM, an **XmlEntityReference** node containing the reference variable `&publisher;` is created, with child nodes representing the content in the entity declared in the DTD.</span></span>  
  
 <span data-ttu-id="5e36c-123">El diagrama siguiente muestra los nodos **XmlEntity** y **XmlText** creados a partir de la declaración de entidad `<!ENTITY publisher "Microsoft Press">`.</span><span class="sxs-lookup"><span data-stu-id="5e36c-123">Using the `<!ENTITY publisher "Microsoft Press">` entity declaration, the following diagram shows the **XmlEntity** and **XmlText** nodes created from this declaration.</span></span>  
  
 <span data-ttu-id="5e36c-124">![Nodos creados a partir de la declaración de entidad](media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")</span><span class="sxs-lookup"><span data-stu-id="5e36c-124">![nodes created from entity declaration](media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")</span></span>  
  
 <span data-ttu-id="5e36c-125">Las diferencias existentes al expandir o no referencias de entidad determinan los nodos generados en el árbol DOM, en la memoria.</span><span class="sxs-lookup"><span data-stu-id="5e36c-125">The differences when entity references are expanded and when they are not makes a difference in what nodes are generated in the DOM tree, in memory.</span></span> <span data-ttu-id="5e36c-126">Las diferencias en los nodos generados se explican en los temas [Se preservan las referencias de entidad](entity-references-are-preserved.md) y [Se expanden las referencias de entidad pero no se preservan](entity-references-are-expanded-and-not-preserved.md).</span><span class="sxs-lookup"><span data-stu-id="5e36c-126">The difference in the nodes that are generated is explained in the topics [Entity References are Preserved](entity-references-are-preserved.md) and [Entity References are Expanded and Not Preserved](entity-references-are-expanded-and-not-preserved.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e36c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e36c-127">See also</span></span>

- [<span data-ttu-id="5e36c-128">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="5e36c-128">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
