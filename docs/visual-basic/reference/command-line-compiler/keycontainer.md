---
title: /keycontainer
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 887e84843201c64f7dd7b056b5e31d5ccd91bf23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="keycontainer"></a>/keycontainer
Especifica un nombre de contenedor de claves para un par de claves que asigna un nombre seguro al ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/keycontainer:container  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`container`|Obligatorio. Archivo contenedor que contiene la clave. Ponga el nombre de archivo entre comillas ("") si el nombre contiene un espacio.|  
  
## <a name="remarks"></a>Comentarios  
 El compilador crea el componente compartible insertando una clave pública en el manifiesto del ensamblado y firma el ensamblado final con la clave privada. Para generar un archivo de clave, escriba `sn -k``file` en la línea de comandos. El `-i` opción instala el par de claves en un contenedor. Para obtener más información, vea [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).  
  
 Si se compila con `/target:module`, el nombre del archivo de clave se mantiene en el módulo y se incorpora en el ensamblado que se crea cuando se compila un ensamblado con [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 También se puede especificar esta opción como un atributo personalizado (<xref:System.Reflection.AssemblyKeyNameAttribute>) en el código fuente de cualquier módulo del Lenguaje Intermedio de Microsoft (MSIL).  
  
 También se puede pasar la información de cifrado al compilador con [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md). Use [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) para firmar el ensamblado de forma parcial.  
  
 Vea [crear y utilizar ensamblados](https://msdn.microsoft.com/library/xwb8f617) para obtener más información sobre cómo firmar un ensamblado.  
  
> [!NOTE]
>  El `/keycontainer` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente compila el archivo de código fuente `Input.vb` y especifica un contenedor de claves.  
  
```  
vbc /keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Ensamblados y Caché global de ensamblados](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
