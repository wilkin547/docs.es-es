---
title: Compatibilidad con los espacios de nombres en DOM
ms.date: 03/30/2017
ms.assetid: f0548ead-0fed-41ee-b33e-117ba900d3bc
ms.openlocfilehash: b3214d77b069b672e8772ec78db51c9d8ee1bf50
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714411"
---
# <a name="namespace-support-in-the-dom"></a>Compatibilidad con los espacios de nombres en DOM

El modelo de objetos de documento XML (DOM) tiene en cuenta completamente al espacio de nombres. Sólo se admiten documentos XML que tengan en cuenta los espacios de nombres. El W3C especifica que las aplicaciones DOM que implementan el nivel 1 pueden no tener en cuenta los espacios de nombres, a diferencia de las características de nivel 2 de DOM, que sí los tienen en cuenta. No obstante, todas las características de DOM XML tienen en cuenta los espacios de nombres, independientemente de si el método proviene del nivel 1 o del nivel 2 de la recomendación de DOM.  
  
 Por ejemplo, en una configuración que no tiene en cuenta el espacio de nombres, si se llama a `setAttribute("A:b", "123")`, como se especifica en la recomendación del nivel 1 de DOM, el resultado no es un atributo con el prefijo `A` y el nombre local `b`. El resultado sería un atributo con el valor `A:b`.  
  
 En un entorno que tenga en cuenta el espacio de nombres, la llamada al nivel 2 de DOM `setAttribute("A:b", "123")` daría como resultado un atributo con el prefijo `A` y el nombre local `b`. DOM de Microsoft .NET Framework funciona de este modo.  
  
 Por tanto, todos los métodos que aceptan un parámetro para el nombre aceptan también un prefijo para calificarlo. El parámetro de nombre, como `A:b` en el método de nivel 1 de DOM **setAttribute**, se analiza como se muestra a continuación:  
  
- Si no hay caracteres de signo de dos puntos (:), el nombre local se configura con el parámetro `name` y el prefijo y URI de espacio de nombres son cadenas vacías.  
  
- Si se encuentra un signo de dos puntos, el nombre se divide en dos partes en función de la posición del primer signo de dos puntos. El prefijo se establece según la cadena que se encuentre antes del signo de dos puntos mientras que el nombre local se establece según la cadena que se encuentre después. Para los métodos que no aceptan un valor de URI de espacio de nombres, éste no se resuelve y sigue establecido como una cadena vacía. De lo contrario, el URI de espacio de nombres se establece como la cadena pasada al método. Si el prefijo no se define, el método **Save** y las propiedades **InnerXml** y **OuterXml** generan un error.  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](xml-document-object-model-dom.md)
