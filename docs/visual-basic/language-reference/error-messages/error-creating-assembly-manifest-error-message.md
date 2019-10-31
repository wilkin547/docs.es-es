---
title: 'Error al crear manifiesto del ensamblado: <error message>'
ms.date: 07/20/2015
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
ms.openlocfilehash: 7ccfb970a0e471b4a7e6808f041dfea2f386e7e9
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197125"
---
# <a name="error-creating-assembly-manifest-error-message"></a>Error al crear el manifiesto del ensamblado: \<mensaje de error >
El compilador Visual Basic llama a Assembly Linker (al. exe, también conocido como ALink) para generar un ensamblado con un manifiesto. El vinculador ha informado de un error en una fase previa a la emisión de la creación del ensamblado.  
  
 Esto puede suceder si existen problemas con el archivo de clave o el contenedor de claves especificado. Para firmar completamente un ensamblado, debe proporcionar un archivo de clave válido que contenga información sobre las claves pública y privada. Para retrasar la firma de un ensamblado, debe activar la casilla **Retrasar solo firma** y proporcionar un archivo de clave válido que contenga información sobre la clave pública. La clave privada no es necesaria cuando un ensamblado tiene la firma retrasada. Para obtener más información, vea [Cómo: Firmar un ensamblado con un nombre seguro](../../../standard/assembly/sign-strong-name.md).  
  
 **Identificador de error:** BC30140  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Examine el mensaje de error citado y consulte el tema [al. exe](../../../framework/tools/al-exe-assembly-linker.md). en el caso de error, explicación más detallada y consejos  
  
2. Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.  
  
## <a name="see-also"></a>Vea también

- [Cómo: Firmar un ensamblado con un nombre seguro](../../../standard/assembly/sign-strong-name.md)
- [Página Firma, Diseñador de proyectos](/visualstudio/ide/reference/signing-page-project-designer)
- [Al. exe](../../../framework/tools/al-exe-assembly-linker.md)
- [Hable con nosotros](/visualstudio/ide/feedback-options)
