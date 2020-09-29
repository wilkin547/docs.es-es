---
title: -nologo
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 5557d681c5e6901592936efd35b3c552d43e39b0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097675"
---
# <a name="-nologo-visual-basic"></a>-nologo (Visual Basic)

Impide que la pancarta de copyright y los mensajes informativos se muestren durante la compilación.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a>Comentarios  

 Si especifica `-nologo`, el compilador no mostrará una pancarta de copyright. De forma predeterminada, `-nologo` no está en vigor.  
  
> [!NOTE]
> La opción `-nologo` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  

 El siguiente código compila `T2.vb` y no muestra ninguna pancarta de copyright.  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
