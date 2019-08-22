---
title: El uso de la instancia predeterminada de una clase en el constructor de la clase puede provocar una llamada recursiva infinita
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: cec3d3d462822ca571cab59a2e4d7e730d2aec46
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664365"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a>El uso de la instancia predeterminada de una clase en el constructor de la clase puede provocar una llamada recursiva infinita
Se usó una instancia predeterminada de una clase en el constructor de la clase. Esto puede derivar en una llamada recursiva infinita, también conocido como bucle infinito.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Quite la instancia predeterminada del constructor de la clase.  
  
## <a name="see-also"></a>Vea también

- [Constructores](../programming-guide/concepts/object-oriented-programming.md#constructors)
