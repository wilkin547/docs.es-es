---
description: "Más información sobre: BC30251: el tipo ' <typename> ' no tiene constructores"
title: El tipo '<typename>' no tiene ningún constructor
ms.date: 07/20/2015
f1_keywords:
- bc30251
- vbc30251
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
ms.openlocfilehash: 3961ba557ad2afd9c94f071b6615573419d7325b
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106584"
---
# <a name="bc30251-type-typename-has-no-constructors"></a>BC30251: el tipo ' \<typename> ' no tiene constructores

Un tipo no admite una llamada a `Sub New()`. Una causa probable puede ser un archivo binario o un compilador dañado.

 **Identificador de error:** BC30251

## <a name="to-correct-this-error"></a>Para corregir este error

1. Si el tipo está en proyecto distinto o en un archivo al que se hace referencia, reinstale el proyecto o archivo en cuestión.

2. Si el tipo se encuentra en el mismo proyecto, vuelva a compilar el ensamblado que contiene dicho tipo.

3. Si el error se repite, vuelva a instalar el compilador de Visual Basic.

4. Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.

## <a name="see-also"></a>Consulte también

- [Objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md)
- [Opciones de comentarios de Visual Studio](/visualstudio/ide/feedback-options)
