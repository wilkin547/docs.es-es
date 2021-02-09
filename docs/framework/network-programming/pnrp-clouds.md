---
description: 'Más información acerca de: Nubes PNRP'
title: Nubes PNRP
ms.date: 03/30/2017
ms.assetid: a82e2bf1-62ab-4c2d-83f3-3217a6aead2e
ms.openlocfilehash: 82e9fe85e019d1ef53fa35ed49d55cd2759b4335
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794902"
---
# <a name="pnrp-clouds"></a>Nubes PNRP

Una "nube" PNRP representa un conjunto de nodos que pueden comunicarse entre sí a través de la red. El término "nube" es sinónimo de "malla del mismo nivel" y "grafo punto a punto".  
  
 La comunicación entre los nodos nunca debería cruzar de una nube a otra. Una instancia <xref:System.Net.PeerToPeer.Cloud> se identifica por su nombre, que distingue mayúsculas de minúsculas. Un único nodo o elemento del mismo nivel puede estar conectado a más de una nube.  
  
 Las nubes están estrechamente unidas a las interfaces de red.  En un equipo de hosts múltiples con dos tarjetas de red asociadas a subredes diferentes, se devolverán tres nubes: una para cada una de las direcciones locales de vínculo por interfaz y una nube de ámbito global única.  
  
 PNRP usa tres "ámbitos" de nube, donde un ámbito es una agrupación de equipos que se pueden encontrar los unos a los otros:  
  
- La nube global se corresponde con el ámbito de dirección IPv6 global y las direcciones globales y representa todos los equipos de Internet IPv6. Solo hay una nube global.  
  
- La nube local de vínculo se corresponde con el ámbito de dirección IPv6 local del vínculo y las direcciones locales del vínculo. Las nubes locales de vínculo están destinadas a un vínculo específico, que suele ser el mismo que la subred asociada localmente. Puede haber varias nubes locales de vínculo.  
  
 La tercera nube, que es la nube específica del sitio, se corresponde con el ámbito de dirección IPv6 de sitio y las direcciones locales del sitio. Esta nube está en desuso, aunque todavía se admite en PNRP.  
  
## <a name="clouds"></a>Nubes  

 Las nubes PNRP se representan mediante instancias de la clase <xref:System.Net.PeerToPeer.Cloud>. Los grupos de nubes usados como elemento del mismo nivel se representan mediante instancias de la clase enumerable <xref:System.Net.PeerToPeer.CloudCollection>. Para obtener las colecciones de nubes PNRP conocidas por el actual elemento del mismo nivel, se debe realizar una llamada al método estático <xref:System.Net.PeerToPeer.Cloud.GetAvailableClouds%2A>.  
  
 Las nubes individuales tienen nombres únicos, representados como una cadena Unicode de 256 caracteres. Estos nombres, junto con el ámbito mencionado anteriormente, se usan para construir instancias únicas de la clase Cloud. Estas instancias se pueden serializar y reconstruir para el uso persistente.  
  
 Una vez que se ha creado u obtenido una instancia Cloud, se pueden registrar con ella nombres del mismo nivel para crear una malla de elementos conocidos del mismo nivel.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.PeerToPeer.Cloud>
- [Protocolo de resolución de nombres del mismo nivel](peer-name-resolution-protocol.md)
