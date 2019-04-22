---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: b0279c5ac658c7d0749f62066abbd705d0a271af
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832421"
---
# <a name="-moduleassemblyname"></a>-moduleassemblyname
Especifica el nombre del ensamblado del que este módulo formará parte.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`assembly_name`|El nombre del ensamblado que formará parte de este módulo.|  
  
## <a name="remarks"></a>Comentarios  
 El compilador procesa los el `-moduleassemblyname` opción únicamente en caso el `-target:module` se ha especificado. Esto hace que el compilador crear un módulo. El módulo creado por el compilador solo es válido para el ensamblado especificado con el `-moduleassemblyname` opción. Si coloca el módulo en un ensamblado diferente, se producirán errores de tiempo de ejecución.  
  
 El `-moduleassemblyname` opción es necesaria sólo cuando se cumplan lo siguiente:  
  
-   Un tipo de datos en el módulo necesita acceso a un `Friend` tipo en un ensamblado de referencia.  
  
-   El ensamblado de referencia ha concedido acceso de ensamblado de confianza al ensamblado en el que se compilará el módulo.  
  
 Para obtener más información acerca de cómo crear un módulo, consulte [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md). Para obtener más información acerca de los ensamblados de confianza, consulte [ensamblados de confianza](../../../standard/assembly/friend-assemblies.md).  
  
> [!NOTE]
>  El `-moduleassemblyname` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde un símbolo del sistema.  
  
## <a name="see-also"></a>Vea también

- [Cómo: Compilar un ensamblado de varios archivos](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-referencia (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [Ensamblados de .NET](../../../standard/assembly/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Ensamblados de confianza](../../../standard/assembly/friend-assemblies.md)
