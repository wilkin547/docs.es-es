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
ms.openlocfilehash: 32ae854e9f1b037a17d9c378ce7ee4a3f9b43ad2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641179"
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
