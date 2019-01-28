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
ms.openlocfilehash: bd89a5fa58507528b2a70efde04ecd2a6f601b39
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605609"
---
# <a name="-keyfile-c-compiler-options"></a>-keyfile (Opciones del compilador de C#)
Especifica el nombre de archivo que contiene la clave criptográfica.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-keyfile:file  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|de esquema JSON|  
|----------|----------------|  
|`file`|El nombre del archivo que contiene la clave de nombre seguro.|  
  
## <a name="remarks"></a>Comentarios  
 Cuando se usa esta opción, el compilador inserta la clave pública del archivo especificado en el manifiesto del ensamblado y, después, firma el último ensamblado con la clave privada. Para generar un archivo de clave, escriba sn -k `file` en la línea de comandos.  
  
 Si se compila con la opción **-target:module**, el nombre del archivo de claves se mantiene en el módulo y se incorpora en el ensamblado que se crea al compilar un ensamblado con la opción [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 También puede pasar la información de cifrado al compilador con [-keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md). Use [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) para firmar el ensamblado de forma parcial.  
  
 Si se especifica tanto -keyfile como -keycontainer (ya sea mediante una opción de línea de comandos o mediante un atributo personalizado) en la misma compilación, el compilador probará primero el contenedor de claves. Si lo consigue, el ensamblado se firma con la información del contenedor de claves. Si el compilador no encuentra el contenedor de claves, probará el archivo especificado con -keyfile. Si lo consigue, el ensamblado se firma con la información del archivo de clave y la información de la clave se instalará en el contenedor de claves (similar a sn -i) de modo que, en la próxima compilación, el contenedor de claves será válido.  
  
 Tenga en cuenta que un archivo de clave puede contener solo la clave pública.  
  
 Para obtener más información, vea [Crear y usar ensamblados con nombre seguro](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) y [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md) (Retrasar la firma de un ensamblado).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Firma**.  
  
3.  Modifique la propiedad **Seleccione un archivo de clave de nombre seguro**.  
  
 Puede tener acceso mediante programación a esta opción del compilador con <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
