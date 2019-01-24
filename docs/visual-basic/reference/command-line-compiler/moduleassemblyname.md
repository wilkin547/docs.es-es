---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 35519be6ddaed64b3e5e2129efb611e0a812ebc3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535183"
---
# <a name="-moduleassemblyname"></a>-moduleassemblyname
Especifica el nombre del ensamblado del que este módulo formará parte.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|de esquema JSON|  
|---|---|  
|`assembly_name`|El nombre del ensamblado que formará parte de este módulo.|  
  
## <a name="remarks"></a>Comentarios  
 El compilador procesa los el `-moduleassemblyname` opción únicamente en caso el `-target:module` se ha especificado. Esto hace que el compilador crear un módulo. El módulo creado por el compilador solo es válido para el ensamblado especificado con el `-moduleassemblyname` opción. Si coloca el módulo en un ensamblado diferente, se producirán errores de tiempo de ejecución.  
  
 El `-moduleassemblyname` opción es necesaria sólo cuando se cumplan lo siguiente:  
  
-   Un tipo de datos en el módulo necesita acceso a un `Friend` tipo en un ensamblado de referencia.  
  
-   El ensamblado de referencia ha concedido acceso de ensamblado de confianza al ensamblado en el que se compilará el módulo.  
  
 Para obtener más información acerca de cómo crear un módulo, consulte [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md). Para obtener más información acerca de los ensamblados de confianza, consulte [ensamblados de confianza](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).  
  
> [!NOTE]
>  El `-moduleassemblyname` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde un símbolo del sistema.  
  
## <a name="see-also"></a>Vea también
- [Cómo: Compilar un ensamblado de múltiples archivos](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-referencia (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [Ensamblados y Caché global de ensamblados](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Ensamblados de confianza](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)
