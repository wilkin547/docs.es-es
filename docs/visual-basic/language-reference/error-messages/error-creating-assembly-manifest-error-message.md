---
title: 'Error al crear el manifiesto de ensamblado: <error message>'
ms.date: 07/20/2015
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
ms.openlocfilehash: 0f67b772bab3104c00510954d01b200aadfa9e8a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296295"
---
# <a name="error-creating-assembly-manifest-error-message"></a>Error al crear el manifiesto del ensamblado: \<mensaje de error >
El compilador de Visual Basic llama a la herramienta Assembly Linker (Al.exe, también denominado Alink) para generar un ensamblado con un manifiesto. El vinculador ha informado de un error en una fase previa a la emisión de la creación del ensamblado.  
  
 Esto puede suceder si existen problemas con el archivo de clave o el contenedor de claves especificado. Para firmar completamente un ensamblado, debe proporcionar un archivo de clave válido que contenga información sobre las claves pública y privada. Para retrasar la firma de un ensamblado, debe activar la casilla **Retrasar solo firma** y proporcionar un archivo de clave válido que contenga información sobre la clave pública. La clave privada no es necesaria cuando un ensamblado tiene la firma retrasada. Para obtener más información, vea [Cómo: Firmar un ensamblado con un nombre seguro](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
 **Identificador de error:** BC30140  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Examine el mensaje de error citado y consulte el tema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md). para el error AL1019 explicación más detallada y consejos  
  
2. Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.  
  
## <a name="see-also"></a>Vea también

- [Filtrar Firma de un ensamblado con un nombre seguro](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)
- [Página Firma, Diseñador de proyectos](/visualstudio/ide/reference/signing-page-project-designer)
- [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)
- [Talk to Us](/visualstudio/ide/talk-to-us)
