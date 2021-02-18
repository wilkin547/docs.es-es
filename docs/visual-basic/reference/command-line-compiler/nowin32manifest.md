---
description: Mas información sobre -nowin32manifest (Visual Basic)
title: -nowin32manifest
ms.date: 03/13/2018
helpviewer_keywords:
- /nowin32manifest compiler option [Visual Basic]
- nowin32manifest compiler option [Visual Basic]
- -nowin32manifest compiler option [Visual Basic]
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
ms.openlocfilehash: 3aa07ee26e47d48da69f1d1b34c8ec4643b7422e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100426725"
---
# <a name="-nowin32manifest-visual-basic"></a>-nowin32manifest (Visual Basic)

Indica al compilador que no inserte ningún manifiesto de la aplicación en el archivo ejecutable.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a>Comentarios  

 Cuando se use esta opción, la aplicación estará sujeta a la virtualización en Windows Vista a menos que proporcione un manifiesto de aplicación en un archivo de recursos Win32 o durante un paso de compilación posterior. Para más información sobre la virtualización, vea [Implementación de ClickOnce en Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 Para más información sobre la creación de manifiestos, vea [-win32manifest (Visual Basic)](win32manifest.md).  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [Página de aplicación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
