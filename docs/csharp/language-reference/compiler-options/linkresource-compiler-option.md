---
description: -linkresource (Opciones del compilador de C#)
title: -linkresource (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /linkresource
helpviewer_keywords:
- /linkresource compiler option [C#]
- linkres compiler option [C#]
- /linkres compiler option [C#]
- -linkres compiler option [C#]
- -linkresource compiler option [C#]
- linkresource compiler option [C#]
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
ms.openlocfilehash: cd1150f3fa0dd0eca4e9352ce3809e73a15126c7
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "89466110"
---
# <a name="-linkresource-c-compiler-options"></a>-linkresource (Opciones del compilador de C#)
Crea un vínculo a un recurso de .NET en el archivo de salida. El archivo de recursos no se agrega al archivo de salida. Esta opción difiere de la opción [-resource](./resource-compiler-option.md), la cual sí inserta un archivo de recursos en el archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a>Argumentos  
 `filename`  
 El archivo de recursos de .NET con el que quiere crear un vínculo desde el ensamblado.  
  
 `identifier` (opcional)  
 El nombre lógico del recurso; nombre que se usa para cargar el recurso. El valor predeterminado es el nombre del archivo.  
  
 `accessibility-modifier` (opcional)  
 La accesibilidad del recurso: pública o privada. El valor predeterminado es public.  
  
## <a name="remarks"></a>Observaciones  
 De manera predeterminada, los recursos vinculados son públicos en el ensamblado cuando se crean con el compilador de C#. Para que sean privados, especifique el modificador de accesibilidad `private`. No se permite ningún otro modificador distinto de `public` o `private`.  
  
 **-linkresource** requiere una de las opciones [-target](./target-compiler-option.md) distinta de **-target:module**.  
  
 Si `filename` es un archivo de recursos de .NET creado, por ejemplo, con [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) o en el entorno de desarrollo, se puede acceder a él con miembros del espacio de nombres <xref:System.Resources>. Para obtener más información, vea <xref:System.Resources.ResourceManager?displayProperty=nameWithType>. Para todos los demás recursos, use los métodos `GetManifestResource` de la clase <xref:System.Reflection.Assembly> para tener acceso al recurso en tiempo de ejecución.  
  
 El archivo especificado en `filename` puede tener cualquier formato. Por ejemplo, se puede hacer que una DLL nativa forme parte de un ensamblado para que se pueda instalar en la caché global de ensamblados y sea accesible desde código administrado del ensamblado. En el segundo de los siguientes ejemplos se muestra cómo hacerlo. También es posible realizar lo mismo en Assembly Linker. En el tercer ejemplo se muestra cómo hacerlo. Para obtener más información, vea [Al.exe (Assembly Linker)](../../../framework/tools/al-exe-assembly-linker.md) y [Trabajar con ensamblados y la memoria caché global de ensamblados](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).  
  
 **-linkres** es la forma abreviada de **-linkresource**.  
  
 Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.  
  
## <a name="example"></a>Ejemplo  
 Para compilar `in.cs` y vincularlo al archivo de recursos `rf.resource`:  
  
```console  
csc -linkresource:rf.resource in.cs  
```  
  
## <a name="example"></a>Ejemplo  
 Compile `A.cs` en un archivo DLL, vincúlelo a un archivo DLL nativo N.dll y coloque el resultado en la caché global de ensamblados (GAC). En este ejemplo, A.dll y N.dll residen en la GAC.  
  
```console  
csc -linkresource:N.dll -t:library A.cs  
gacutil -i A.dll  
```  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo hace lo mismo que el anterior, pero usa las opciones de Assembly Linker.  
  
```console  
csc -t:module A.cs  
al -out:A.dll A.netmodule -link:N.dll
gacutil -i A.dll  
```  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Al.exe (Assembly Linker)](../../../framework/tools/al-exe-assembly-linker.md)
- [Trabajar con ensamblados y la memoria caché global de ensamblados](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
