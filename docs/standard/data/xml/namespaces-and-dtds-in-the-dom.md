---
title: Espacios de nombres y DTD en DOM
ms.date: 03/30/2017
ms.assetid: 1e9b55c4-76ad-4f54-8d96-7ce4b4cf1e05
ms.openlocfilehash: 42bd30e7eea2ec0a3e1aa6846196c3280697efdf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714554"
---
# <a name="namespaces-and-dtds-in-the-dom"></a><span data-ttu-id="e9034-102">Espacios de nombres y DTD en DOM</span><span class="sxs-lookup"><span data-stu-id="e9034-102">Namespaces and DTDs in the DOM</span></span>

<span data-ttu-id="e9034-103">Las definiciones de tipo de documento (DTD) complican la compatibilidad del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e9034-103">Document type definitions (DTDs) complicate namespace support.</span></span> <span data-ttu-id="e9034-104">Por ejemplo, el siguiente código XML contiene atributos predeterminados que incluyen signos de dos puntos en su nombre.</span><span class="sxs-lookup"><span data-stu-id="e9034-104">For example, the following XML contains default attributes containing colons in their names.</span></span>  
  
```xml  
<!ATTLIST item x:id CDATA #IMPLIED>  
```  
  
 <span data-ttu-id="e9034-105">A continuación se presentan resoluciones posibles en caso de que se permita esta construcción.</span><span class="sxs-lookup"><span data-stu-id="e9034-105">The following are possible resolutions if this construct is allowed:</span></span>  
  
- <span data-ttu-id="e9034-106">`x:` se trata como un prefijo de espacio de nombres, pero este prefijo debe poder resolverse mediante una declaración de espacio de nombres `xmlns:x`, que debe existir también en algún lugar de la DTD.</span><span class="sxs-lookup"><span data-stu-id="e9034-106">The `x:` is treated as a namespace prefix, but this prefix must be resolvable using an `xmlns:x` namespace declaration, which must also exist somewhere in the DTD.</span></span> <span data-ttu-id="e9034-107">Es un error asignar este prefijo a algo distinto en el documento de instancia.</span><span class="sxs-lookup"><span data-stu-id="e9034-107">It is an error to map this prefix to something different in the instance document.</span></span>  
  
- <span data-ttu-id="e9034-108">`x:` se trata como un prefijo de espacio de nombres, pero este prefijo se resuelve siempre en el contexto de elementos de instancia.</span><span class="sxs-lookup"><span data-stu-id="e9034-108">The `x:` is treated as a namespace prefix, but this prefix is always resolved in the context of the instance elements.</span></span> <span data-ttu-id="e9034-109">Esto significa que el prefijo podría asignar realmente diferentes identificadores uniformes de recursos (URI) de espacio de nombres, en función del ámbito del espacio de nombres en el que aparezca el elemento `item`.</span><span class="sxs-lookup"><span data-stu-id="e9034-109">This means the prefix could actually map to different namespace Uniform Resource Identifiers (URIs), depending on the namespace scope in which the `item` element appears.</span></span> <span data-ttu-id="e9034-110">Este comportamiento es más predecible que la resolución proporcionada en la viñeta anterior, pero tiene otras ramificaciones complicadas debido a que es necesario que los atributos predeterminados se materialicen.</span><span class="sxs-lookup"><span data-stu-id="e9034-110">This behavior is more predictable than the resolution given in the earlier bullet, but it has other complicated ramifications because it requires the default attributes be materialized.</span></span>  
  
- <span data-ttu-id="e9034-111">El signo de dos puntos se pasa por alto porque está en una DTD y el nombre del atributo es `x:y`, sin prefijo y sin identificador URI de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e9034-111">The colon is ignored because it is in a DTD, and the name of the attribute is `x:y`, no prefix and no namespace URI.</span></span>  
  
- <span data-ttu-id="e9034-112">El signo de dos puntos del atributo predeterminado inicia una excepción que indica que no se admiten signos de dos puntos en los nombres dentro de una DTD.</span><span class="sxs-lookup"><span data-stu-id="e9034-112">The colon in the default attribute throws an exception, saying that colons in names inside a DTD are not supported.</span></span> <span data-ttu-id="e9034-113">Esto provoca un comportamiento predecible, pero implica que no se pueden cargar muchas de las DTD publicadas del W3C.</span><span class="sxs-lookup"><span data-stu-id="e9034-113">This results in a predictable behavior, but means you cannot load many of the World Wide Web Consortium (W3C) published DTDs.</span></span>  
  
- <span data-ttu-id="e9034-114">Cuando el usuario solicita la validación de la DTD, se desactiva la compatibilidad con los espacios de nombres en todo el documento.</span><span class="sxs-lookup"><span data-stu-id="e9034-114">When the user requests DTD validation, namespace support for the entire document is turned off.</span></span> <span data-ttu-id="e9034-115">Esto permite cargar la DTD del W3C y ocasiona un comportamiento predecible.</span><span class="sxs-lookup"><span data-stu-id="e9034-115">This makes it possible to load W3C DTDs and results in a predictable behavior.</span></span>  
  
 <span data-ttu-id="e9034-116">XML en Microsoft .NET Framework implementa la segunda opción para tener la máxima compatibilidad con el W3C.</span><span class="sxs-lookup"><span data-stu-id="e9034-116">The XML in the Microsoft .NET Framework implements the second option for maximum W3C compatibility.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9034-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9034-117">See also</span></span>

- [<span data-ttu-id="e9034-118">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="e9034-118">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
