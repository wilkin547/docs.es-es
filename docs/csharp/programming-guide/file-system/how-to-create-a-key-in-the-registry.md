---
title: "C&#243;mo: Crear una clave en el Registro (Visual C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "claves, crear en el Registro"
  - "claves del Registro, crear [C#]"
  - "Registro, añadir claves y valores [C#]"
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# C&#243;mo: Crear una clave en el Registro (Visual C#)
En este ejemplo se agrega el par de valores "Name" e "Isabella", del Registro del usuario actual, bajo la clave "Names".  
  
## Ejemplo  
  
```  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## Compilar el código  
  
-   Copie el código y péguelo en el método `Main` de una aplicación de consola.  
  
-   Sustituya el parámetro `Names` por el nombre de una clave que exista directamente bajo el nodo HKEY\_CURRENT\_USER del Registro.  
  
-   Sustituya el parámetro `Nam`e por el nombre de un valor que exista directamente bajo el nodo Names.  
  
## Programación eficaz  
 Examine la estructura del Registro para buscar la ubicación adecuada para la clave.  Por ejemplo, puede que desee abrir la clave de Software del usuario actual y crear una clave con el nombre de su empresa.  A continuación, agregue los valores del Registro a la clave de su empresa.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El nombre de la clave es null.  
  
-   El usuario no tiene permiso para crear claves del Registro.  
  
-   El nombre de la clave supera el límite de 255 caracteres.  
  
-   La clave está cerrada.  
  
-   La clave del Registro es de sólo lectura.  
  
## Seguridad de .NET Framework  
 Resulta más seguro escribir datos en la carpeta de usuario — `Microsoft.Win32.Registry.CurrentUser` — que en el equipo local — `Microsoft.Win32.Registry.LocalMachine`.  
  
 A la hora de crear valores de Registro, deberá decidir qué hacer si coinciden con otros ya existentes.  Es posible que otro proceso, probablemente malintencionado, haya creado el valor y tenga acceso a él.  Cuando ponga datos en el valor del Registro, los datos estarán disponibles para el otro proceso.  Para evitar esto, utilice el método `Overload:Microsoft.Win32.RegistryKey.GetValue`.  Devuelve null si la clave ya no existe.  
  
 Aunque la clave del Registro esté protegida por listas de control de acceso \(ACL\), no es seguro almacenar en ella datos secretos, como contraseñas, en forma de texto sin formato.  
  
## Vea también  
 <xref:System.IO?displayProperty=fullName>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Registro y sistema de archivos](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)   
 [Lectura, escritura y cancelación del Registro con C\#](http://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)