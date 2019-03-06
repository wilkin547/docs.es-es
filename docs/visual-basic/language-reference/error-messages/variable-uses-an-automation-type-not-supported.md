---
title: La variable utiliza un tipo de Automation no compatible con Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vbrID458
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
ms.openlocfilehash: d369930752989ff69ee17359e85118f3af4b70b5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369206"
---
# <a name="variable-uses-an-automation-type-not-supported-in-visual-basic"></a>La variable utiliza un tipo de Automation no compatible con Visual Basic

Se intentó utilizar una variable definida en una biblioteca de tipos o biblioteca de objetos que tiene un tipo de datos no compatible con Visual Basic.

## <a name="to-correct-this-error"></a>Para corregir este error

- Usar una variable de un tipo reconocido por Visual Basic.

     O bien

- Si se produce este error mientras usa `FileGet` o `FileGetObject`, asegúrese de que el archivo que está intentando usar se escribió para con `FilePut` o `FilePutObject`.

## <a name="see-also"></a>Vea también

- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
