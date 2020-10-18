---
title: El tipo '<typename>' no tiene ningún constructor
ms.date: 07/20/2015
f1_keywords:
- bc30251
- vbc30251
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
ms.openlocfilehash: 249bcb7020f26c7c43d560e91ef7a34e4dc64470
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161184"
---
# <a name="bc30251-type-typename-has-no-constructors"></a>BC30251: el tipo ' \<typename> ' no tiene constructores

Un tipo no admite una llamada a `Sub New()`. Una causa probable puede ser un archivo binario o un compilador dañado.

 **Identificador de error:** BC30251

## <a name="to-correct-this-error"></a>Para corregir este error

1. Si el tipo está en proyecto distinto o en un archivo al que se hace referencia, reinstale el proyecto o archivo en cuestión.

2. Si el tipo se encuentra en el mismo proyecto, vuelva a compilar el ensamblado que contiene dicho tipo.

3. Si el error se repite, vuelva a instalar el compilador de Visual Basic.

4. Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.

## <a name="see-also"></a>Vea también

- [Objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md)
- [Hable con nosotros](/visualstudio/ide/feedback-options)
