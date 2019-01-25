---
title: -nowin32manifest (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /nowin32manifest compiler option [Visual Basic]
- nowin32manifest compiler option [Visual Basic]
- -nowin32manifest compiler option [Visual Basic]
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
ms.openlocfilehash: d0a51b2af8b1d8fcf9f0df8dae457a0d3b570a1b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744731"
---
# <a name="-nowin32manifest-visual-basic"></a>-nowin32manifest (Visual Basic)
Indica al compilador que no inserte ningún manifiesto de la aplicación en el archivo ejecutable.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-nowin32manifest  
```  
  
## <a name="remarks"></a>Comentarios  
 Cuando se use esta opción, la aplicación estará sujeta a la virtualización en Windows Vista a menos que proporcione un manifiesto de aplicación en un archivo de recursos Win32 o durante un paso de compilación posterior. Para más información sobre la virtualización, vea [Implementación de ClickOnce en Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 Para más información sobre la creación de manifiestos, vea [-win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md).  
  
## <a name="see-also"></a>Vea también
- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Página de aplicación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
