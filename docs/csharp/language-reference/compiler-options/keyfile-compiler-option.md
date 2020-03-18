---
title: -keyfile (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /keyfile
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
ms.openlocfilehash: bf271cc6b6887e930911071d4603b51daed55e61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970260"
---
# <a name="-keyfile-c-compiler-options"></a>-keyfile (Opciones del compilador de C#)
Especifica el nombre de archivo que contiene la clave criptográfica.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-keyfile:file  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|----------|----------------|  
|`file`|El nombre del archivo que contiene la clave de nombre seguro.|  
  
## <a name="remarks"></a>Comentarios  
 Cuando se usa esta opción, el compilador inserta la clave pública del archivo especificado en el manifiesto del ensamblado y, después, firma el último ensamblado con la clave privada. Para generar un archivo de clave, escriba sn -k `file` en la línea de comandos.  
  
 Si se compila con la opción **-target:module**, el nombre del archivo de claves se mantiene en el módulo y se incorpora en el ensamblado que se crea al compilar un ensamblado con la opción [-addmodule](./addmodule-compiler-option.md).  
  
 También puede pasar la información de cifrado al compilador con [-keycontainer](./keycontainer-compiler-option.md). Use [-delaysign](./delaysign-compiler-option.md) para firmar el ensamblado de forma parcial.  
  
 Si se especifica tanto -keyfile como -keycontainer (ya sea mediante una opción de línea de comandos o mediante un atributo personalizado) en la misma compilación, el compilador probará primero el contenedor de claves. Si lo consigue, el ensamblado se firma con la información del contenedor de claves. Si el compilador no encuentra el contenedor de claves, probará el archivo especificado con -keyfile. Si lo consigue, el ensamblado se firma con la información del archivo de clave y la información de la clave se instalará en el contenedor de claves (similar a sn -i) de modo que, en la próxima compilación, el contenedor de claves será válido.  
  
 Tenga en cuenta que un archivo de clave puede contener solo la clave pública.  
  
 Para obtener más información, vea [Crear y usar ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md) y [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md) (Retrasar la firma de un ensamblado).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1. Abra la página **Propiedades** del proyecto.  
  
2. Haga clic en la página de propiedades **Firma**.  
  
3. Modifique la propiedad **Seleccione un archivo de clave de nombre seguro**.  
  
 Puede tener acceso mediante programación a esta opción del compilador con <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de proyectos y de soluciones](/visualstudio/ide/managing-project-and-solution-properties)
