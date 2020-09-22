---
title: No se admiten literales XML ni propiedades XML en código incrustado en ASP.NET
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: 861677636f9a73015b26efec30df728d07fbdf72
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870213"
---
# <a name="xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a>No se admiten literales XML ni propiedades XML en código incrustado en ASP.NET

No se admiten literales XML ni propiedades XML en código incrustado dentro de ASP.NET. Para usar las características XML, mueva el código al código subyacente.  
  
 Un literal XML o una propiedad de eje XML se define dentro del código incrustado ( `<%= =>` ) en un archivo ASP.net.  
  
 **Identificador de error:** BC31200  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Mueva el código que incluye el literal XML o la propiedad de eje XML a un archivo de código subyacente de ASP.NET.  
  
## <a name="see-also"></a>Consulte también

- [Literales XML](../xml-literals/index.md)
- [Propiedades de eje XML](../xml-axis/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
