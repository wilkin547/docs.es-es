---
title: /moduleassemblyname
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0d9a5307970ac745b4f102d0008e64b985c00e52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="moduleassemblyname"></a>/moduleassemblyname
Especifica el nombre del ensamblado del que este módulo formará parte.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`assembly_name`|El nombre del ensamblado que formará parte de este módulo.|  
  
## <a name="remarks"></a>Comentarios  
 Los procesos de compilador la `/moduleassemblyname` opción únicamente en caso el `/target:module` se ha especificado la opción. Esto hace que el compilador crear un módulo. El módulo creado por el compilador solo es válido para el ensamblado especificado con el `/moduleassemblyname` opción. Si coloca el módulo en un ensamblado diferente, se producirán errores de tiempo de ejecución.  
  
 El `/moduleassemblyname` opción es necesaria sólo cuando se cumple la siguiente:  
  
-   Un tipo de datos en el módulo necesita acceso a un `Friend` tipo en un ensamblado de referencia.  
  
-   El ensamblado que se hace referencia ha concedido acceso de ensamblado de confianza para el ensamblado en el que se generará el módulo.  
  
 Para obtener más información acerca de cómo crear un módulo, consulte [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md). Para obtener más información acerca de ensamblados de confianza, consulte [Friend (ensamblados)](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).  
  
> [!NOTE]
>  El `/moduleassemblyname` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible solo cuando se compila desde un símbolo del sistema.  
  
## <a name="see-also"></a>Vea también  
 [Compilar un ensamblado de varios archivos](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [/main](../../../visual-basic/reference/command-line-compiler/main.md)  
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [Ensamblados y Caché global de ensamblados](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Ensamblados de confianza](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)
