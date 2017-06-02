---
title: "C&#243;mo: Hacer referencia a un ensamblado con nombre seguro | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ensamblados [.NET Framework], con nombre seguro"
  - "enlace de ensamblado, con nombre seguro"
  - "referencia a un ensamblado en tiempo de compilación"
  - "ensamblados con nombre seguro, referencias en tiempo de compilación"
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Hacer referencia a un ensamblado con nombre seguro
El proceso para hacer referencia a los tipos o recursos de un ensamblado de nombre seguro es, por lo general, transparente.  La referencia se puede hacer en tiempo de compilación o en tiempo de ejecución para permitir el enlace.  
  
 Una referencia en tiempo de compilación se produce cuando se indica al compilador que el ensamblado haga referencia de forma explícita a otro ensamblado.  Cuando se usa la referencia en tiempo de compilación, el compilador obtiene automáticamente la clave pública del ensamblado de nombre seguro de destino y la ubica en la referencia al ensamblado del ensamblado que se está compilando.  
  
> [!NOTE]
>  Un ensamblado con nombre seguro sólo puede utilizar tipos de otros ensamblados con nombre seguro.  De lo contrario, se pondría en peligro la seguridad del ensamblado con nombre seguro.  
  
### Para hacer una referencia en tiempo de compilación a un ensamblado de nombre seguro  
  
1.  En el símbolo del sistema, escriba el siguiente comando:  
  
     \<*compiler command*\> **\/reference:**\<*assembly name*\>  
  
     En este comando, *compiler command* es el comando del compilador para el lenguaje que utilice, y *assembly name* es el nombre del ensamblado fuerte\- denominado que hace referencia.  También se pueden usar otras opciones de compilador, por ejemplo la opción **\/t:library** para crear un ensamblado de biblioteca.  
  
 En el ejemplo siguiente se crea un ensamblado denominado `myAssembly.dll` que hace referencia a un ensamblado de nombre seguro denominado `myLibAssembly.dll` desde un módulo de código denominado `myAssembly.cs`.  
  
```  
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  
  
### Para hacer una referencia en tiempo de ejecución a un ensamblado de nombre seguro  
  
1.  Cuando se hace una referencia en tiempo de ejecución a un ensamblado con nombre seguro \(por ejemplo, usando el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> o <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName>\), es necesario usar el nombre para mostrar del ensamblado con nombre seguro al que se hace referencia.  La sintaxis de un nombre para mostrar es:  
  
     \<*assembly name*\>**,** \<*version number*\>**,** \<*culture*\>**,** \<*public key token*\>  
  
     Por ejemplo:  
  
    ```  
    myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33   
    ```  
  
     En este ejemplo, `PublicKeyToken` es el formato hexadecimal del token de clave pública.  Si no hay ningún valor de referencia cultural, use `Culture=neutral`.  
  
 En el ejemplo de código siguiente se muestra cómo se usa esta información con el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>.  
  
 [!code-cpp[Assembly.Load1#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.Load1/CPP/load2.cpp#3)]
 [!code-csharp[Assembly.Load1#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.Load1/CS/load2.cs#3)]
 [!code-vb[Assembly.Load1#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.Load1/VB/load2.vb#3)]  
  
 Se puede imprimir el formato hexadecimal de la clave pública y del token de clave pública de un ensamblado concreto usando el siguiente comando de [Nombre seguro \(Sn.exe\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md):  
  
 **sn \-Tp \<** *assembly* **\>**  
  
 Si se tiene un archivo de clave pública, se puede utilizar el siguiente comando \(advierta la diferencia entre mayúsculas y minúsculas en la opción de la línea de comandos\):  
  
 **sn \-tp \<** *assembly* **\>**  
  
## Vea también  
 [Crear y utilizar ensamblados con nombre seguro](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)