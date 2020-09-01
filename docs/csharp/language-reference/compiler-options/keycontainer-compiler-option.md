---
description: -keycontainer (Opciones del compilador de C#)
title: -keycontainer (Opciones del compilador de C#)
ms.date: 05/16/2018
f1_keywords:
- /keycontainer
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
ms.openlocfilehash: 8b11380683159b7792149558a5dd432707ba3818
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125506"
---
# <a name="-keycontainer-c-compiler-options"></a>-keycontainer (Opciones del compilador de C#)
Especifica el nombre del contenedor de claves criptográficas.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-keycontainer:string  
```  
  
## <a name="arguments"></a>Argumentos  
 `string`  
 El nombre del contenedor de claves de nombre seguro.  
  
## <a name="remarks"></a>Observaciones  
 Cuando se utiliza la opción **-keycontainer**, el compilador crea un componente que se puede compartir. El compilador inserta una clave pública del contenedor especificado en el manifiesto del ensamblado y firma el último ensamblado con la clave privada. Para generar un archivo de claves, escriba `sn -k file` en la línea de comandos. `sn -i` instala el par de claves en un contenedor. Esta opción no se admite cuando el compilador se ejecuta en CoreCLR. Para firmar un ensamblado al compilar en CoreCLR, utilice la opción [-keyfile](keyfile-compiler-option.md).
  
 Si se compila con [-target:module](./target-module-compiler-option.md), el nombre del archivo de claves se mantiene en el módulo y se incorpora al ensamblado al compilar este módulo en un ensamblado con [-addmodule](./addmodule-compiler-option.md).  
  
 También se puede especificar esta opción como un atributo personalizado (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) en el código fuente de cualquier módulo del Lenguaje Intermedio de Microsoft (MSIL).  
  
 También se puede pasar la información de cifrado al compilador con [-keyfile](./keyfile-compiler-option.md). Use [-delaysign](./delaysign-compiler-option.md) si quiere agregar la clave pública al manifiesto del ensamblado pero retrasar la firma del ensamblado hasta que se haya probado.  
  
 Para obtener más información, vea [Crear y usar ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md) y [Retraso de la firma de un ensamblado](../../../standard/assembly/delay-sign.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1. Esta opción del compilador no está disponible en el entorno de desarrollo de Visual Studio.  
  
 Puede tener acceso mediante programación a esta opción del compilador con <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.  
  
## <a name="see-also"></a>Vea también

- [Opción -keyfile del compilador de C#](keyfile-compiler-option.md)
- [Opciones del compilador de C#](index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
