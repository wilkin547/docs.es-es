---
title: "Cómo: Crear una clave en el Registro (Visual C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
caps.latest.revision: 14
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3a377a85acdc31b426171ab6583bff92b24889b3
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-key-in-the-registry-visual-c"></a>Cómo: Crear una clave en el Registro (Visual C#)
En este ejemplo se agrega el par de valores "Name" e "Isabella" al Registro del usuario actual en la clave "Names".  
  
## <a name="example"></a>Ejemplo  
  
```  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   Copie el código y péguelo en el método `Main` de una aplicación de consola.  
  
-   Sustituya el parámetro `Names` por el nombre de una clave que exista directamente en el nodo HKEY_CURRENT_USER del Registro.  
  
-   Sustituya el parámetro `Nam` por el nombre de un valor que exista directamente en el nodo Names.  
  
## <a name="robust-programming"></a>Programación sólida  
 Examine la estructura del Registro para buscar una ubicación adecuada para la clave. Por ejemplo, es posible que quiera abrir la clave Software del usuario actual y crear una clave con el nombre de la empresa. Luego agregue los valores del Registro a la clave de la empresa.  
  
 Las condiciones siguientes pueden generar una excepción:  
  
-   Que el nombre de la clave sea nulo.  
  
-   Que el usuario no tenga permisos para crear claves del Registro.  
  
-   Que el nombre de la clave supere el límite de 255 caracteres.  
  
-   Que la clave esté cerrada.  
  
-   Que la clave del Registro sea de solo lectura.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Es más seguro escribir datos en la carpeta de usuario (`Microsoft.Win32.Registry.CurrentUser`) que en el equipo local (`Microsoft.Win32.Registry.LocalMachine`).  
  
 Cuando se crea un valor del Registro, se debe decidir qué hacer si ese valor ya existe. Puede que otro proceso, quizás uno malintencionado, ya haya creado el valor y tenga acceso a él. Al colocar datos en el valor del Registro, estos están a disposición del otro proceso. Para evitarlo, use el método `Overload:Microsoft.Win32.RegistryKey.GetValue` . Si la clave aún no existe, devuelve null.  
  
 No es seguro almacenar secretos, como contraseñas, en el Registro como texto sin formato, aunque la clave del Registro esté protegida mediante listas de control de acceso (ACL).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO?displayProperty=fullName>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Registro y sistema de archivos (Guía de programación de C#)](../../../csharp/programming-guide/file-system/index.md)   
 [Read, write and delete from the registry with C# (Leer, escribir y eliminar en el Registro con C#)](http://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)
