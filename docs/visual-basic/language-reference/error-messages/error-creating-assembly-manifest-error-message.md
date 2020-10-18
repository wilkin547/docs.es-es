---
title: 'Error al crear manifiesto del ensamblado: <error message>'
ms.date: 07/20/2015
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
ms.openlocfilehash: a772167966c4ec858197cc2032f4ae3d4e86070c
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163420"
---
# <a name="bc30140-error-creating-assembly-manifest-error-message"></a>BC30140: error al crear el manifiesto del ensamblado: \<error message>

El compilador Visual Basic llama a Assembly Linker (Al.exe, también conocido como ALink) para generar un ensamblado con un manifiesto. El vinculador ha informado de un error en una fase previa a la emisión de la creación del ensamblado.

 Esto puede suceder si existen problemas con el archivo de clave o el contenedor de claves especificado. Para firmar completamente un ensamblado, debe proporcionar un archivo de clave válido que contenga información sobre las claves pública y privada. Para retrasar la firma de un ensamblado, debe activar la casilla **Retrasar solo firma** y proporcionar un archivo de clave válido que contenga información sobre la clave pública. La clave privada no es necesaria cuando un ensamblado tiene la firma retrasada. Para más información, vea: [Cómo: Firmar un ensamblado con un nombre seguro](../../../standard/assembly/sign-strong-name.md).

 **Identificador de error:** BC30140

## <a name="to-correct-this-error"></a>Para corregir este error

1. Examine el mensaje de error citado y consulte el tema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md). en el caso de error, explicación más detallada y consejos

2. Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.

## <a name="see-also"></a>Vea también

- [Cómo: Firma de un ensamblado con un nombre seguro](../../../standard/assembly/sign-strong-name.md)
- [Página Firma, Diseñador de proyectos](/visualstudio/ide/reference/signing-page-project-designer)
- [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)
- [Hable con nosotros](/visualstudio/ide/feedback-options)
