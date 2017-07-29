---
title: "Cómo: Crear archivos o carpetas (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
caps.latest.revision: 22
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 150190eeef829bd0431eeea7789025b9905553e3
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a>Cómo: Crear archivos o carpetas (Guía de programación de C#)
Puede crear una carpeta en el equipo mediante programación, crear una subcarpeta, crear un archivo en la subcarpeta y escribir datos en el archivo.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]  
  
 Si la carpeta ya existe, <xref:System.IO.Directory.CreateDirectory%2A> no efectúa ninguna acción y no se devuelve ninguna excepción. Sin embargo, <xref:System.IO.File.Create%2A?displayProperty=fullName> reemplaza un archivo existente por otro nuevo. En el ejemplo se usa una instrucción `if`-`else` para evitar que se sustituya un archivo existente.  
  
 Al realizar los siguientes cambios en el ejemplo, puede especificar diferentes resultados en función de si ya existe un archivo con un nombre determinado. Si no existe ese archivo, el código crea uno. Si ese archivo ya existe, el código anexa datos a ese archivo.  
  
-   Especifique un nombre de archivo no aleatorio.  
  
    ```csharp  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
    ```  
  
-   Sustituya la instrucción `if`-`else` por la instrucción `using` en el código siguiente.  
  
    ```csharp  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))   
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
    ```  
  
 Ejecute el ejemplo varias veces para comprobar que los datos se agreguen al archivo cada vez.  
  
 Para obtener más valores `FileMode` que puede probar, consulte <xref:System.IO.FileMode>.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El nombre de la carpeta tiene un formato incorrecto. Por ejemplo, contiene caracteres no válidos o solo tiene espacios en blanco (clase <xref:System.ArgumentException>). Use la clase <xref:System.IO.Path> para crear nombres de ruta válidos.  
  
-   La carpeta principal de la que se va a crear es de solo lectura (clase <xref:System.IO.IOException>).  
  
-   El nombre de la carpeta es `null` (clase <xref:System.ArgumentNullException>).  
  
-   El nombre de la carpeta es demasiado largo (clase <xref:System.IO.PathTooLongException>).  
  
-   El nombre de la carpeta es solo un carácter de dos puntos, ":" (clase <xref:System.IO.PathTooLongException>).  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 En los casos de confiabilidad parcial, es posible que se devuelva una instancia de la clase <xref:System.Security.SecurityException>.  
  
 Si no tiene permiso para crear la carpeta, el ejemplo devuelve una instancia de la clase <xref:System.UnauthorizedAccessException>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO?displayProperty=fullName>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Registro y sistema de archivos (Guía de programación de C#)](../../../csharp/programming-guide/file-system/index.md)

