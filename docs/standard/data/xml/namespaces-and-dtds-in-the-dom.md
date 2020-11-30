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
# <a name="namespaces-and-dtds-in-the-dom"></a>Espacios de nombres y DTD en DOM

Las definiciones de tipo de documento (DTD) complican la compatibilidad del espacio de nombres. Por ejemplo, el siguiente código XML contiene atributos predeterminados que incluyen signos de dos puntos en su nombre.  
  
```xml  
<!ATTLIST item x:id CDATA #IMPLIED>  
```  
  
 A continuación se presentan resoluciones posibles en caso de que se permita esta construcción.  
  
- `x:` se trata como un prefijo de espacio de nombres, pero este prefijo debe poder resolverse mediante una declaración de espacio de nombres `xmlns:x`, que debe existir también en algún lugar de la DTD. Es un error asignar este prefijo a algo distinto en el documento de instancia.  
  
- `x:` se trata como un prefijo de espacio de nombres, pero este prefijo se resuelve siempre en el contexto de elementos de instancia. Esto significa que el prefijo podría asignar realmente diferentes identificadores uniformes de recursos (URI) de espacio de nombres, en función del ámbito del espacio de nombres en el que aparezca el elemento `item`. Este comportamiento es más predecible que la resolución proporcionada en la viñeta anterior, pero tiene otras ramificaciones complicadas debido a que es necesario que los atributos predeterminados se materialicen.  
  
- El signo de dos puntos se pasa por alto porque está en una DTD y el nombre del atributo es `x:y`, sin prefijo y sin identificador URI de espacio de nombres.  
  
- El signo de dos puntos del atributo predeterminado inicia una excepción que indica que no se admiten signos de dos puntos en los nombres dentro de una DTD. Esto provoca un comportamiento predecible, pero implica que no se pueden cargar muchas de las DTD publicadas del W3C.  
  
- Cuando el usuario solicita la validación de la DTD, se desactiva la compatibilidad con los espacios de nombres en todo el documento. Esto permite cargar la DTD del W3C y ocasiona un comportamiento predecible.  
  
 XML en Microsoft .NET Framework implementa la segunda opción para tener la máxima compatibilidad con el W3C.  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](xml-document-object-model-dom.md)
