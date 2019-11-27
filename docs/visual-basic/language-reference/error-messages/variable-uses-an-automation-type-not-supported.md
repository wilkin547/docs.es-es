---
title: La variable utiliza un tipo de automatización no compatible
ms.date: 07/20/2015
f1_keywords:
- vbrID458
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
ms.openlocfilehash: 944c0c63cd0d7ae7f9ff770fd123231464af1eaf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344827"
---
# <a name="variable-uses-an-automation-type-not-supported-in-visual-basic"></a>La variable utiliza un tipo de Automation no compatible con Visual Basic

Ha intentado usar una variable definida en una biblioteca de tipos o una biblioteca de objetos que tiene un tipo de datos no admitido por Visual Basic.

## <a name="to-correct-this-error"></a>Para corregir este error

- Use una variable de un tipo reconocido por Visual Basic.

     O bien,

- Si se produce este error al usar `FileGet` o `FileGetObject`, asegúrese de que el archivo que está intentando usar se ha escrito con `FilePut` o `FilePutObject`.

## <a name="see-also"></a>Vea también

- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
