---
title: El tipo '<typename>' no tiene ningún constructor
ms.date: 07/20/2015
f1_keywords:
- bc30251
- vbc30251
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
ms.openlocfilehash: 8fc173182d062c80ffde15b1e7210644d37f8f66
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875116"
---
# <a name="type-typename-has-no-constructors"></a>El tipo '\<typename>' no tiene ningún constructor

Un tipo no admite una llamada a `Sub New()`. Una causa probable puede ser un archivo binario o un compilador dañado.  
  
 **Identificador de error:** BC30251  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Si el tipo está en proyecto distinto o en un archivo al que se hace referencia, reinstale el proyecto o archivo en cuestión.  
  
2. Si el tipo se encuentra en el mismo proyecto, vuelva a compilar el ensamblado que contiene dicho tipo.  
  
3. Si el error se repite, vuelva a instalar el compilador de Visual Basic.  
  
4. Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.  
  
## <a name="see-also"></a>Consulte también

- [Objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md)
- [Hable con nosotros](/visualstudio/ide/feedback-options)
