---
description: -filealign (Opciones del compilador de C#)
title: -filealign (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /filealign
helpviewer_keywords:
- /alignment compiler option [C#]
- filealign compiler option [C#]
- -filealign compiler option [C#]
- /sections compiler option [C#]
- alignment compiler option [C#]
- sections compiler option [C#]
- -sections compiler option [C#]
- /filealign compiler option [C#]
- file sharing [C#]
- -alignment compiler option [C#]
- section alignment [C#]
ms.assetid: 15cf1c98-3798-4ced-9f08-60619308a073
ms.openlocfilehash: 4b61217a3d6812ea3ab036f82d49bba05c20629e
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "91173248"
---
# <a name="-filealign-c-compiler-options"></a>-filealign (Opciones del compilador de C#)

La opción **-filealign** permite especificar el tamaño de las secciones en el archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a>Argumentos  

 `number`  
 Un valor que especifica el tamaño de las secciones del archivo de salida. Los valores válidos son 512, 1024, 2048, 4096 y 8192. Estos valores están en bytes.  
  
## <a name="remarks"></a>Comentarios  

 Cada sección se alineará en un límite que es un múltiplo del valor **-filealign**. No hay ningún valor predeterminado fijo. Si no se especifica **-filealign**, Common Language Runtime elige un valor predeterminado en tiempo de compilación.  
  
 Al especificar el tamaño de la sección, el tamaño del archivo de salida se ve afectado. Modificar el tamaño de la sección puede ser útil para los programas que se ejecutan en dispositivos más pequeños.  
  
 Use [DUMPBIN](/cpp/build/reference/dumpbin-options) para ver información sobre las secciones en el archivo de salida.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1. Abra la página **Propiedades** del proyecto.  
  
2. Haga clic en la página de propiedades de **Compilar**.  
  
3. Haga clic en el botón **Avanzadas** .  
  
4. Modifique la propiedad **Alineación de archivo**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
