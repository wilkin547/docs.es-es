---
title: -reference (Opciones del compilador de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /reference
dev_langs:
- CSharp
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
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 7e33ed084c560470a486ebbb25035a59ddc18565
ms.openlocfilehash: 11bb7fc9490879714542bfbd77a81d58e7d8e8ed
ms.contentlocale: es-es
ms.lasthandoff: 03/31/2017

---
# <a name="reference-c-compiler-options"></a>/reference (Opciones del compilador de C#)
La opción **/reference** hace que el compilador importe información de tipo [public](../../../csharp/language-reference/keywords/public.md) del archivo especificado al proyecto actual, lo que permite hacer referencia a metadatos de los archivos de ensamblado especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
/reference:[alias=]filename  
/reference:filename  
```  
  
## <a name="arguments"></a>Argumentos  
 `filename`  
 El nombre de un archivo que contiene un manifiesto del ensamblado. Para importar más de un archivo, incluya una opción **/reference** diferente para cada archivo.  
  
 `alias`  
 Un identificador de C# válido que representa un espacio de nombres raíz que contendrá todos los espacios de nombres del ensamblado.  
  
## <a name="remarks"></a>Comentarios  
 Para importar desde más de un archivo, incluya una opción **/reference** para cada archivo.  
  
 Los archivos que se importen deben contener un manifiesto; el archivo de salida debe haberse compilado con una de las opciones [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) distinta de [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).  
  
 **/r** es la forma abreviada de **/reference**.  
  
 Use [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) para importar metadatos de un archivo de salida que no contenga un manifiesto de ensamblado.  
  
 Si hace referencia a un ensamblado (ensamblado A) que hace referencia a otro ensamblado (ensamblado B), debe hacer referencia al ensamblado B si:  
  
-   Un tipo que se use del ensamblado A hereda de un tipo o implementa una interfaz del ensamblado B.  
  
-   Se invoca un campo, una propiedad, un evento o un método que tiene un tipo de parámetro o un tipo de valor devuelto del ensamblado B.  
  
 Use [/lib](../../../csharp/language-reference/compiler-options/lib-compiler-option.md) para especificar el directorio en el que se encuentran una o varias de las referencias de ensamblado. En el tema **/lib** también se describen los directorios en los que el compilador busca ensamblados.  
  
 Para que el compilador reconozca un tipo de un ensamblado (y no de un módulo), debe obligársele a que resuelva el tipo, lo que se puede conseguir si se define una instancia del tipo. Existen otras formas de que el compilador resuelva nombres de tipos en un ensamblado; por ejemplo, si se hereda de un tipo de un ensamblado, el compilador reconocerá el nombre del tipo.  
  
 A veces es necesario hacer referencia a dos versiones diferentes del mismo componente desde un ensamblado. Para ello, use la subopción de alias en el modificador **/reference** de cada archivo para distinguir entre los dos archivos. Este alias se usará como calificador para el nombre del componente y se resolverá en el componente de uno de los archivos.  
  
 De forma predeterminada se usa el archivo de respuesta (.rsp) csc, que hace referencia a los ensamblados de .NET Framework usados habitualmente. Use [/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) si no quiere que el compilador use csc.rsp.  
  
> [!NOTE]
> En Visual Studio, use el cuadro de diálogo **Agregar referencia**. Para obtener más información, consulte [Cómo: Agregar o quitar referencias usando el Administrador de referencias](https://docs.microsoft.com/en-us/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager). Para garantizar un comportamiento equivalente entre agregar referencias mediante `/reference` y agregar referencias mediante el cuadro de diálogo **Agregar referencia**, establezca la propiedad **Incrustar tipos de interoperabilidad** en **False** para el ensamblado que se va a agregar. El valor predeterminado de la propiedad es **True**.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo usar la característica [alias externo](../../../csharp/language-reference/keywords/extern-alias.md).  
  
 Compile el archivo de origen e importe los metadatos desde `grid.dll` y `grid20.dll`, que se han compilado previamente. Los dos archivos DLL contienen versiones independientes del mismo componente y se usan dos **/reference** con opciones de alias para compilar el archivo de origen. Las opciones tiene este aspecto:  
  
 /reference:GridV1=grid.dll y /reference:GridV2=grid20.dll  
  
 Esto configura los alias externos "GridV1" y "GridV2" que se usan en el programa por medio de una instrucción extern:  
  
```csharp  
extern alias GridV1;  
extern alias GridV2;  
// Using statements go here.  
```  
  
 Una vez hecho esto, se puede hacer referencia al control de cuadrícula de grid.dll anteponiendo GridV1 al nombre del control, de esta forma:  
  
```csharp  
GridV1::Grid  
```  
  
 Además, se puede hacer referencia al control de cuadrícula de grid20.dll anteponiendo GridV2 al nombre del control, de esta forma:  
  
```csharp  
GridV2::Grid   
```  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)   
 [NO ESTÁ EN LA COMPILACIÓN Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
