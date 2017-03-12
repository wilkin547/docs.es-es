---
title: "C&#243;mo: Recorrer en iteraci&#243;n un &#225;rbol de directorio (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "iteración de archivos [C#]"
  - "recorrer en iteración las carpetas [C#]"
ms.assetid: c4be4a75-6b1b-46a7-9d38-bab353091ed7
caps.latest.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 10
---
# C&#243;mo: Recorrer en iteraci&#243;n un &#225;rbol de directorio (Gu&#237;a de programaci&#243;n de C#)
La frase "recorrer en iteración un árbol de directorios" significa obtener acceso a cada uno de los archivos de todos los subdirectorios anidados bajo una carpeta raíz especificada hasta un nivel de profundidad cualquiera.  No es necesario abrir cada archivo.  Puede limitarse a recuperar el nombre del archivo o subdirectorio como `string`, o bien recuperar información adicional en forma de objeto <xref:System.IO.DirectoryInfo?displayProperty=fullName> o <xref:System.IO.FileInfo?displayProperty=fullName>.  
  
> [!NOTE]
>  En Windows, los términos "directorio" y "carpeta" se utilizan indistintamente.  La mayor parte de la documentación y del texto de la interfaz de usuario utiliza el término "carpeta", pero la biblioteca de clases de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] utiliza el término "directorio".  
  
 En el caso más simple, en el que sabe con seguridad que tiene permisos de acceso para todos los directorios incluidos en una raíz especificada, puede utilizar el marcador `System.IO.SearchOption.AllDirectories`.  Este marcador devuelve todos los subdirectorios anidados que coinciden con el modelo especificado.  En el ejemplo siguiente se muestra cómo utilizar este marcador.  
  
```c#  
root.GetDirectories("*.*", System.IO.SearchOption.AllDirectories);  
```  
  
 El punto débil de este enfoque es que si uno de los subdirectorios incluidos en la raíz especificada produce una excepción <xref:System.IO.DirectoryNotFoundException> o <xref:System.UnauthorizedAccessException>, se produce un error de todo el método y no devuelve ningún directorio.  Lo mismo sucede al utilizar el método <xref:System.IO.DirectoryInfo.GetFiles%2A>.  Si tiene que controlar estas excepciones en subcarpetas específicas, debe recorrer manualmente el árbol de directorios, como se muestra en los ejemplos siguientes.  
  
 Al recorrer manualmente un árbol de directorios, puede controlar primero los subdirectorios \(*recorrido en preorden*\) o los archivos \(*recorrido en postorden*\).  Al realizar un recorrido en preorden, se recorre todo el árbol bajo la carpeta actual antes de recorrer en iteración los archivos que están directamente en esa carpeta.  Los ejemplos que se proporcionan más adelante en este documento realizan un recorrido en postorden, si bien puede modificarlos fácilmente para que realicen un recorrido en preorden.  
  
 Otra opción consiste en utilizar la recursividad o un recorrido basado en la pila.  Los ejemplos que se proporcionan más adelante en este documento muestran ambos enfoques.  
  
 Si tiene que realizar diversas operaciones en los archivos y las carpetas, puede dividir estos ejemplos en partes mediante la refactorización de la operación en funciones separadas que se puedan invocar utilizando un solo delegado.  
  
> [!NOTE]
>  Los sistemas de archivos NTFS pueden contener *puntos de reanálisis* en forma de *puntos de unión*, *vínculos simbólicos* y *vínculos físicos*.  Los métodos de .NET Framework como <xref:System.IO.DirectoryInfo.GetFiles%2A> y <xref:System.IO.DirectoryInfo.GetDirectories%2A> no devolverán ningún subdirectorio situado bajo un punto de reanálisis.  Este comportamiento protege frente al riesgo de provocar un bucle infinito cuando dos puntos de reanálisis se hacen referencia entre sí.  En general, debería ser muy cuidadoso al tratar con puntos de reanálisis para asegurarse de no modificar o eliminar archivos involuntariamente.  Si desea obtener un control preciso de los puntos de reanálisis, utilice la invocación de plataforma o código nativo para llamar directamente a los métodos de sistema de archivos Win32 adecuados.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo recorrer un árbol de directorios mediante recursividad.  El enfoque recursivo resulta elegante, pero puede producir una excepción de desbordamiento de la pila si el árbol de directorios es grande y cuenta con muchos elementos anidados.  
  
 Las excepciones concretas que se controlan y las acciones determinadas que se realizan en cada archivo o carpeta se proporcionan simplemente como ejemplos.  Debe modificar este código para que se ajuste a sus requisitos concretos.  Para obtener más información, vea los comentarios del código.  
  
 [!code-cs[csFilesandFolders#1](../../../csharp/programming-guide/file-system/codesnippet/csharp/csFilesFolders/FileIteration.cs#1)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo recorrer en iteración los archivos y las carpetas de un árbol de directorios sin utilizar la recursividad.  Esta técnica utiliza el tipo de colección genérica <xref:System.Collections.Generic.Stack%601>, que es una pila de tipo LIFO \(último en entrar, primero en salir\).  
  
 Las excepciones concretas que se controlan y las acciones determinadas que se realizan en cada archivo o carpeta se proporcionan simplemente como ejemplos.  Debe modificar este código para que se ajuste a sus requisitos concretos.  Para obtener más información, vea los comentarios del código.  
  
 [!code-cs[csFilesandFolders#2](../../../csharp/programming-guide/file-system/codesnippet/csharp/csFilesFolders/FileIteration.cs#2)]  
  
 Generalmente se tarda mucho tiempo en comprobar cada carpeta para determinar si su aplicación tiene permiso para abrirla.  Por consiguiente, el ejemplo de código incluye esa parte de la operación en un bloque `try/catch`.  Puede modificar el bloque `catch` de forma que, cuando se le deniegue el acceso a una carpeta, intente elevar sus permisos y obtener acceso a ésta de nuevo.  Como norma, detecte solamente las excepciones que puede controlar sin dejar la aplicación en un estado desconocido.  
  
 Si debe almacenar el contenido de un árbol de directorios, ya sea en memoria o en el disco, la mejor opción es almacenar solamente la propiedad <xref:System.IO.FileSystemInfo.FullName%2A> \(de tipo `string`\) para cada archivo.  Después, puede utilizar esta cadena para crear un nuevo objeto <xref:System.IO.DirectoryInfo> o <xref:System.IO.FileInfo>, según sea necesario, o para abrir cualquier archivo que requiera un procesamiento adicional.  
  
## Programación eficaz  
 Un código eficaz de iteración de archivos debe tener en cuenta las numerosas dificultades del sistema de archivos.  Para obtener más información, vea [NTFS Technical Reference](http://go.microsoft.com/fwlink/?LinkId=79488).  
  
## Vea también  
 <xref:System.IO>   
 [LINQ and File Directories](../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)   
 [Registro y sistema de archivos](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)