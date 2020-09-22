---
title: El procedimiento Let de la propiedad no está definido y el procedimiento Get no ha devuelto un objeto
ms.date: 07/20/2015
f1_keywords:
- vbrID451
ms.assetid: 8542382a-689f-4e1b-abc0-c1e2dadb92f4
ms.openlocfilehash: fbeaa224ea9e095f86c37e571492d83bc98b4397
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871088"
---
# <a name="property-let-procedure-not-defined-and-property-get-procedure-did-not-return-an-object"></a>El procedimiento Let de la propiedad no está definido y el procedimiento Get no ha devuelto un objeto

Ciertas propiedades, métodos y operaciones solo se pueden aplicar a los `Collection` objetos. Especificó una operación o propiedad que es exclusiva de las colecciones, pero el objeto no es una colección.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Compruebe la ortografía del nombre del objeto o de la propiedad, o Compruebe que el objeto es un `Collection` objeto.  
  
2. Observe el `Add` método utilizado para agregar el objeto a la colección para asegurarse de que la sintaxis es correcta y que los identificadores se han escrito correctamente.  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.Collection>
