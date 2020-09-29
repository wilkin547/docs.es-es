---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 9fb9287f9472d4b33eff4cb601aff5eed370b2c0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91065572"
---
# <a name="-moduleassemblyname"></a>-moduleassemblyname

Especifica el nombre del ensamblado del que este módulo formará parte.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`assembly_name`|Nombre del ensamblado del que este módulo formará parte.|  
  
## <a name="remarks"></a>Comentarios  

 El compilador procesa la opción `-moduleassemblyname` solo si se ha especificado la opción `-target:module`. Esto hace que el compilador cree un módulo. El módulo creado por el compilador es válido únicamente en el ensamblado especificado con la opción `-moduleassemblyname`. Si el módulo se coloca en otro ensamblado, se producirán errores en tiempo de ejecución.  
  
 La opción `-moduleassemblyname` solo es necesaria cuando se cumplen las siguientes condiciones:  
  
- Un tipo de datos del módulo necesita acceso a un tipo `Friend` en un ensamblado al que se hace referencia.  
  
- El ensamblado al que se hace referencia ha concedido acceso de ensamblado de confianza al ensamblado en el que el módulo se compilará.  
  
 Para más información sobre cómo crear un módulo, vea [-target (Visual Basic)](target.md). Para más información sobre los ensamblados de confianza, vea [Ensamblados de confianza](../../../standard/assembly/friend.md).  
  
> [!NOTE]
> La opción `-moduleassemblyname` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde un símbolo del sistema.  
  
## <a name="see-also"></a>Vea también

- [Cómo: Compilar un ensamblado de varios archivos](../../../framework/app-domains/build-multifile-assembly.md)
- [Compilador de línea de comandos de Visual Basic](index.md)
- [-target (Visual Basic)](target.md)
- [-main](main.md)
- [-reference (Visual Basic)](reference.md)
- [-addmodule](addmodule.md)
- [Ensamblados de .NET](../../../standard/assembly/index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
- [Ensamblados de confianza](../../../standard/assembly/friend.md)
