---
title: "/reference (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/reference"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/r compiler option [C#]"
  - "reference compiler option [C#]"
  - "r compiler option [C#]"
  - "/reference compiler option [C#]"
  - "-r compiler option [C#]"
  - "metadata import [C#]"
  - "public type information [C#]"
  - "-reference compiler option [C#]"
ms.assetid: 8d13e5b0-abf6-4c46-bf71-2daf2cd0a6c4
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# /reference (C# Compiler Options)
La opción **\/reference** hace que el compilador importe información de tipo [public](../../../csharp/language-reference/keywords/public.md) al archivo especificado del proyecto actual, permitiéndole así hacer referencia a los metadatos desde los archivos de ensamblado especificados.  
  
## Sintaxis  
  
```  
/reference:[alias=]filename  
/reference:filename  
```  
  
## Argumentos  
 `filename`  
 El nombre de un archivo que contiene un manifiesto del ensamblado.  Para importar más de un archivo, incluya una opción **\/reference** independiente para cada archivo.  
  
 `alias`  
 Un identificador de C\# válido que representa al espacio de nombres raíz que contendrá todos los espacios de nombres del ensamblado.  
  
## Comentarios  
 Para importar más de un archivo, incluya una opción **\/reference** para cada archivo.  
  
 Los archivos que importe deben contener un manifiesto, y el archivo de salida debe haberse compilado con una de las opciones [\/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) diferentes de  [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).  
  
 **\/r** es la forma abreviada de **\/reference**.  
  
 Utilice [addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) para importar metadatos de un archivo de salida que no contenga un manifiesto del ensamblado.  
  
 Si hace referencia a un ensamblado \(Ensamblado A\) que, a su vez, hace referencia a otro ensamblado \(Ensamblado B\), también deberá hacer referencia al ensamblado B si:  
  
-   Un tipo utilizado en el Ensamblado A hereda de un tipo o implementa una interfaz del Ensamblado B.  
  
-   Se invoca un campo, una propiedad, un evento o un método que devuelve un tipo o tiene un tipo de parámetro de Ensamblado B.  
  
 Utilice [\/lib](../../../csharp/language-reference/compiler-options/lib-compiler-option.md) para especificar el directorio en el que se encuentran una o varias de las referencias de ensamblados.  El tema **\/lib** trata también sobre los directorios donde el compilador busca ensamblados.  
  
 Para que el compilador reconozca un tipo en un ensamblado, y no en un módulo, debe obligársele a que resuelva el tipo, lo que se puede conseguir definiendo una instancia del tipo.  Existen otras formas de que el compilador resuelva nombres de tipos en un ensamblado; por ejemplo, si hereda de un tipo de un ensamblado, el compilador reconocerá el nombre del tipo.  
  
 A veces, es necesario hacer referencia a dos versiones diferentes del mismo componente desde un solo ensamblado.  Para ello, utilice la subopción de alias en el modificador **\/reference** para que cada archivo distinga entre los dos archivos.  Dicho alias se utilizará como calificador del nombre del componente y se resolverá como tal componente en uno de los archivos.  
  
 El archivo de respuesta csc.rsp, que hace referencia a los ensamblados utilizados comúnmente en .NET Framework, es el predeterminado.  Use [\/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) si no desea que el compilador use csc.rsp.  
  
> [!NOTE]
>  En Visual Studio, use el cuadro de diálogo **Agregar referencia**.  Para obtener más información, vea [Cómo: Agregar o quitar referencias utilizando el cuadro de diálogo Agregar referencia](http://msdn.microsoft.com/es-es/3bd75d61-f00c-47c0-86a2-dd1f20e231c9).  En Visual Studio 2010 y versiones posteriores, para garantizar que la adición de referencias mediante la opción `/reference` y mediante el cuadro de diálogo **Agregar referencia** tienen un comportamiento equivalente, la propiedad **Incrustar tipos de interoperabilidad** debe establecerse en **False** para el ensamblado que se va a agregar.  **True** es el valor predeterminado de esa propiedad.  
  
## Ejemplo  
 En este ejemplo se muestra cómo usar la característica de [alias externo](../../../csharp/language-reference/keywords/extern-alias.md).  
  
 Compile el archivo de código fuente e importe los metadatos de `grid.dll` y `grid20.dll`, ``  que se compilaron anteriormente.  Los dos archivos DLL contienen versiones independientes del mismo componente y el usuario utiliza dos modificadores **\/reference** con opciones de alias para compilar el archivo de código fuente.  Las opciones tienen la apariencia siguiente:  
  
 \/reference:GridV1\=grid.dll y \/reference:GridV2\=grid20.dll  
  
 Con ello se crean los alias externos "GridV1" y "GridV2" que podrá utilizar en su programa por medio de una instrucción extern:  
  
```  
extern alias GridV1;  
extern alias GridV2;  
// Using statements go here.  
```  
  
 Una vez hecho esto, puede hacer referencia al control de cuadrícula de grid.dll anteponiendo GridV1 al nombre de control, de la siguiente forma:  
  
```  
GridV1::Grid  
```  
  
 Además, puede hacer referencia al control de cuadrícula de grid20.dll anteponiendo GridV2 al nombre de control, de la siguiente forma:  
  
```  
GridV2::Grid   
```  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)