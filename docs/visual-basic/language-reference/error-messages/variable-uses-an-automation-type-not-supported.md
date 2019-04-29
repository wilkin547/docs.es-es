---
title: La variable utiliza un tipo de Automation no compatible con Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vbrID458
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
ms.openlocfilehash: d369930752989ff69ee17359e85118f3af4b70b5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766901"
---
# <a name="variable-uses-an-automation-type-not-supported-in-visual-basic"></a>La variable utiliza un tipo de Automation no compatible con Visual Basic

Se intentó utilizar una variable definida en una biblioteca de tipos o biblioteca de objetos que tiene un tipo de datos no compatible con Visual Basic.

## <a name="to-correct-this-error"></a>Para corregir este error

- Usar una variable de un tipo reconocido por Visual Basic.

     -o bien-

- Si se produce este error mientras usa `FileGet` o `FileGetObject`, asegúrese de que el archivo que está intentando usar se escribió para con `FilePut` o `FilePutObject`.

## <a name="see-also"></a>Vea también

- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
