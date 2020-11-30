---
description: -reference (Opciones del compilador de C#)
title: -reference (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /reference
helpviewer_keywords:
- /r compiler option [C#]
- reference compiler option [C#]
- r compiler option [C#]
- /reference compiler option [C#]
- -r compiler option [C#]
- metadata import [C#]
- public type information [C#]
- -reference compiler option [C#]
ms.assetid: 8d13e5b0-abf6-4c46-bf71-2daf2cd0a6c4
ms.openlocfilehash: cd7346ae4094a84a398306394f771e040dd7b72f
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193795"
---
# <a name="-reference-c-compiler-options"></a>-reference (Opciones del compilador de C#)

La opción **-reference** hace que el compilador importe información de tipo [public](../keywords/public.md) del archivo especificado al proyecto actual, lo que permite hacer referencia a metadatos de los archivos de ensamblado especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-reference:[alias=]filename  
-reference:filename  
```  
  
## <a name="arguments"></a>Argumentos  

 `filename`  
 El nombre de un archivo que contiene un manifiesto del ensamblado. Para importar más de un archivo, incluya una opción **-reference** diferente para cada archivo.  
  
 `alias`  
 Un identificador de C# válido que representa un espacio de nombres raíz que contendrá todos los espacios de nombres del ensamblado.  
  
## <a name="remarks"></a>Comentarios  

 Para importar desde más de un archivo, incluya una opción **-reference** para cada archivo.  
  
 Los archivos que se importen deben contener un manifiesto; el archivo de salida debe haberse compilado con una de las opciones [-target](./target-compiler-option.md) distinta de [-target:module](./target-module-compiler-option.md).  
  
 **-r** es la forma abreviada de **-reference**.  
  
 Use [-addmodule](./addmodule-compiler-option.md) para importar metadatos de un archivo de salida que no contenga un manifiesto de ensamblado.  
  
 Si hace referencia a un ensamblado (ensamblado A) que hace referencia a otro ensamblado (ensamblado B), debe hacer referencia al ensamblado B si:  
  
- Un tipo que se use del ensamblado A hereda de un tipo o implementa una interfaz del ensamblado B.  
  
- Se invoca un campo, una propiedad, un evento o un método que tiene un tipo de parámetro o un tipo de valor devuelto del ensamblado B.  
  
 Use [-lib](./lib-compiler-option.md) para especificar el directorio en el que se encuentran una o varias de las referencias de ensamblado. En el tema **-lib** también se describen los directorios en los que el compilador busca ensamblados.  
  
 Para que el compilador reconozca un tipo de un ensamblado (y no de un módulo), debe obligársele a que resuelva el tipo, lo que se puede conseguir si se define una instancia del tipo. Existen otras formas de que el compilador resuelva nombres de tipos en un ensamblado; por ejemplo, si se hereda de un tipo de un ensamblado, el compilador reconocerá el nombre del tipo.  
  
 A veces es necesario hacer referencia a dos versiones diferentes del mismo componente desde un ensamblado. Para ello, use la subopción de alias en el modificador **-reference** de cada archivo para distinguir entre los dos archivos. Este alias se usará como calificador para el nombre del componente y se resolverá en el componente de uno de los archivos.  
  
 De forma predeterminada se usa el archivo de respuesta (.rsp) csc, que hace referencia a los ensamblados de .NET Framework usados habitualmente. Use [-noconfig](./noconfig-compiler-option.md) si no quiere que el compilador use csc.rsp.  
  
> [!NOTE]
> En Visual Studio, use el cuadro de diálogo **Agregar referencia**. Para obtener más información, consulta [Procedimiento para agregar o quitar referencias mediante el Administrador de referencias](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager). Para garantizar un comportamiento equivalente entre agregar referencias mediante `-reference` y agregar referencias mediante el cuadro de diálogo **Agregar referencia**, establezca la propiedad **Incrustar tipos de interoperabilidad** en **False** para el ensamblado que se va a agregar. El valor predeterminado de la propiedad es **True**.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se muestra cómo usar la característica [alias externo](../keywords/extern-alias.md).  
  
 Compile el archivo de origen e importe los metadatos desde `grid.dll` y `grid20.dll`, que se han compilado previamente. Los dos archivos DLL contienen versiones independientes del mismo componente y se usan dos **-reference** con opciones de alias para compilar el archivo de origen. Las opciones tiene este aspecto:  

```console
-reference:GridV1=grid.dll -reference:GridV2=grid20.dll  
```
  
 Esto configura los alias externos `GridV1` y `GridV2`, que se usan en el programa por medio de una instrucción `extern`:  
  
```csharp  
extern alias GridV1;  
extern alias GridV2;  
// Using statements go here.  
```  
  
 Una vez hecho esto, se puede hacer referencia al control de cuadrícula desde `grid.dll` si se antepone `GridV1` al nombre del control, de esta forma:  
  
```csharp  
GridV1::Grid  
```  
  
 Además, se puede hacer referencia al control de cuadrícula desde `grid20.dll` si se antepone `GridV2` al nombre del control, de esta forma:  
  
```csharp  
GridV2::Grid
```  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
