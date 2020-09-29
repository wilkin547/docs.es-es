---
title: -out
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 7c013270c8a6b7c2b28f02766df7437b43075dd2
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91098909"
---
# <a name="-out-visual-basic"></a>-out (Visual Basic)

Especifica el nombre del archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`filename`|Obligatorio. El nombre del archivo de salida creado por el compilador. Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").|  
  
## <a name="remarks"></a>Comentarios  

 Especifique el nombre completo y la extensión del archivo que se va a crear. Si no lo hace, el archivo .exe toma su nombre del archivo de código fuente que contiene el procedimiento `Sub Main` y el archivo .dll toma el suyo del primer archivo de código fuente.  
  
 Si especifica un nombre de archivo sin la extensión .exe o .dll, el compilador agrega automáticamente la extensión, en función del valor especificado para la opción del compilador `-target`.  
  
|Para establecer -out en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Aplicación** .<br />3.  Modifique el valor del cuadro **Nombre del ensamblado**.|  
  
## <a name="example"></a>Ejemplo  

 El código siguiente compila `T2.vb` y crea el archivo de salida `T2.exe`.  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [-target (Visual Basic)](target.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
