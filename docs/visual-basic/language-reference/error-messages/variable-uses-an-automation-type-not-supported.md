---
title: Variable uses an Automation type not supported
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

You tried to use a variable defined in a type library or object library that has a data type not supported by Visual Basic.

## <a name="to-correct-this-error"></a>Para corregir este error

- Use a variable of a type recognized by Visual Basic.

     o bien

- If you encounter this error while using `FileGet` or `FileGetObject`, make sure the file you are trying to use was written to with `FilePut` or `FilePutObject`.

## <a name="see-also"></a>Vea también

- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
