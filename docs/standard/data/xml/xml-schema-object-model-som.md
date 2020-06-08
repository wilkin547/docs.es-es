---
title: Modelo de objetos de esquema XML (SOM)
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: a897a599-ffd1-43f9-8807-e58c8a7194cd
ms.openlocfilehash: 1de9fdf9950ba3ae356779ca802afb71f24a345e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290323"
---
# <a name="xml-schema-object-model-som"></a><span data-ttu-id="b531e-102">Modelo de objetos de esquema XML (SOM)</span><span class="sxs-lookup"><span data-stu-id="b531e-102">XML Schema Object Model (SOM)</span></span>
<span data-ttu-id="b531e-103">Un esquema XML es una herramienta potente y compleja que sirve para crear y validar estructuras en documentos conforme a XML.</span><span class="sxs-lookup"><span data-stu-id="b531e-103">An XML schema is a powerful and complex tool for creating and validating structure in compliant XML documents.</span></span> <span data-ttu-id="b531e-104">De forma similar al modelado de datos en una base de datos relacional, un esquema proporciona una forma de definir la estructura de los documentos XML al especificar los elementos que se pueden utilizar en los documentos, así como la estructura y los tipos que deben seguir estos elementos con el fin de ser válidos en ese esquema específico.</span><span class="sxs-lookup"><span data-stu-id="b531e-104">Similar to data modeling in a relational database, a schema provides a way to define the structure of XML documents, by specifying the elements that can be used in the documents, as well as the structure and types that these elements must follow in order to be valid for that specific schema.</span></span>  
  
 <span data-ttu-id="b531e-105">El Modelo de objetos de esquema (SOM) incluye un conjunto de clases en el espacio de nombres <xref:System.Xml.Schema?displayProperty=nameWithType> que le permiten leer un esquema desde un archivo o crear un esquema en memoria mediante programación.</span><span class="sxs-lookup"><span data-stu-id="b531e-105">The Schema Object Model (SOM) provides a set of classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace that allow you to read a schema from a file or to programmatically create a schema in-memory.</span></span> <span data-ttu-id="b531e-106">Luego, el esquema se puede atravesar, editar, compilar, validar o escribir en un archivo.</span><span class="sxs-lookup"><span data-stu-id="b531e-106">The schema can then be traversed, editing, compiled, validated, or written to a file.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b531e-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b531e-107">In This Section</span></span>  
 [<span data-ttu-id="b531e-108">Información general sobre el Modelo de objetos de esquema XML</span><span class="sxs-lookup"><span data-stu-id="b531e-108">XML Schema Object Model Overview</span></span>](xml-schema-object-model-overview.md)  
 <span data-ttu-id="b531e-109">Describe el Modelo de objetos de esquema (SOM) y las características y clases que incluye.</span><span class="sxs-lookup"><span data-stu-id="b531e-109">Describes the Schema Object Model (SOM) and the features and classes it provides.</span></span>  
  
 [<span data-ttu-id="b531e-110">Lectura y escritura de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="b531e-110">Reading and Writing XML Schemas</span></span>](reading-and-writing-xml-schemas.md)  
 <span data-ttu-id="b531e-111">Describe cómo leer y escribir esquemas XML desde archivos u otros orígenes.</span><span class="sxs-lookup"><span data-stu-id="b531e-111">Describes how to read and write XML schemas from files or other sources.</span></span>  
  
 [<span data-ttu-id="b531e-112">Compilación de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="b531e-112">Building XML Schemas</span></span>](building-xml-schemas.md)  
 <span data-ttu-id="b531e-113">Describe cómo utilizar las clases del espacio de nombres <xref:System.Xml.Schema?displayProperty=nameWithType> para compilar esquemas XML en memoria.</span><span class="sxs-lookup"><span data-stu-id="b531e-113">Describes how to use the classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace to build XML schemas in-memory.</span></span>  
  
 [<span data-ttu-id="b531e-114">Recorrido de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="b531e-114">Traversing XML Schemas</span></span>](traversing-xml-schemas.md)  
 <span data-ttu-id="b531e-115">Describe cómo atravesar un esquema XML para obtener acceso a los elementos, atributos y tipos que están almacenados en el SOM.</span><span class="sxs-lookup"><span data-stu-id="b531e-115">Describes how to traverse an XML schema to access the elements, attributes, and types stored in the SOM.</span></span>  
  
 [<span data-ttu-id="b531e-116">Edición de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="b531e-116">Editing XML Schemas</span></span>](editing-xml-schemas.md)  
 <span data-ttu-id="b531e-117">Describe cómo editar un esquema XML.</span><span class="sxs-lookup"><span data-stu-id="b531e-117">Describes how to edit an XML schema.</span></span>  
  
 [<span data-ttu-id="b531e-118">Inclusión o importación de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="b531e-118">Including or Importing XML Schemas</span></span>](including-or-importing-xml-schemas.md)  
 <span data-ttu-id="b531e-119">Describe cómo incluir o importar otros esquemas XML para complementar la estructura del esquema que los incluye o los importa.</span><span class="sxs-lookup"><span data-stu-id="b531e-119">Describes how to include or import other XML schemas to supplement the structure of the schema that includes or imports them.</span></span>
