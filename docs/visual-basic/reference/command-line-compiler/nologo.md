---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 07e1718554b158635b9d8b04958834e804e1fe9f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964376"
---
# <a name="-nologo-visual-basic"></a>-nologo (Visual Basic)
Suprime la presentación de la pancarta de copyright y los mensajes informativos durante la compilación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-nologo  
```  
  
## <a name="remarks"></a>Comentarios  
 Si especifica `-nologo`, el compilador no mostrará un titular de copyright. De forma predeterminada, `-nologo` no está en vigor.  
  
> [!NOTE]
> La `-nologo` opción no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente se compila `T2.vb` y no se muestra un banner de copyright.  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
