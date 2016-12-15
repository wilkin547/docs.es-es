---
title: "/linkresource (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/linkresource"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/linkresource compiler option [C#]"
  - "linkres compiler option [C#]"
  - "/linkres compiler option [C#]"
  - "-linkres compiler option [C#]"
  - "-linkresource compiler option [C#]"
  - "linkresource compiler option [C#]"
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /linkresource (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Crea un vínculo con un recurso de .NET Framework en el archivo de salida.  El archivo de recursos no se agrega al archivo de salida.  Esta opción difiere de la opción [\/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md), la cual sí incrusta un archivo de recursos en el archivo de salida.  
  
## Sintaxis  
  
```  
/linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## Argumentos  
 `filename`  
 Archivo de recursos de .NET Framework con el que desea crear un vínculo desde el ensamblado.  
  
 `identifier` \(opcional\)  
 Nombre lógico del recurso; nombre que se usa para cargar el recurso.   El valor predeterminado es el nombre del archivo.  
  
 `accessibility-modifier` \(opcional\)  
 Accesibilidad del recurso: pública o privada.  El valor predeterminado es que sea pública.  
  
## Comentarios  
 De forma predeterminada, los recursos vinculados son públicos en el ensamblado cuando se crean con el compilador de C\#.   Para que sean privados, especifique  el modificador de accesibilidad `private`.  No se permite ningún otro modificador distinto de `public` o `private`.  
  
 **\/linkresource** requiere una de las opciones de [\/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) distinta de **\/target:module**.  
  
 Si `filename` es un archivo de recursos de .NET Framework creado, por ejemplo, con [Resgen.exe](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) o en el entorno de desarrollo, se puede obtener acceso a él con miembros del espacio de nombres <xref:System.Resources>.  Para obtener más información, vea <xref:System.Resources.ResourceManager?displayProperty=fullName>.  Para todos los demás recursos, utilice los métodos `GetManifestResource`\* de la clase <xref:System.Reflection.Assembly> para obtener acceso al recurso en tiempo de ejecución.  
  
 El archivo especificado en `filename` puede tener cualquier formato.  Por ejemplo, se puede hacer que una DLL nativa forme parte de un ensamblado para que se pueda instalar en la caché global de ensamblados y sea accesible desde código administrado del ensamblado.  El segundo de los siguientes ejemplos muestra cómo hacerlo.  También es posible llevarlo a cabo en Assembly Linker.  El tercer ejemplo indica cómo.  Para obtener más información, vea [Al.exe \(Assembly Linker\)](../Topic/Al.exe%20\(Assembly%20Linker\).md) y [Trabajar con ensamblados y la memoria caché global de ensamblados](../Topic/Working%20with%20Assemblies%20and%20the%20Global%20Assembly%20Cache.md).  
  
 **\/linkres** es la forma abreviada de **\/linkresource**.  
  
 Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.  
  
## Ejemplo  
 Para compilar `in.cs` y vincularlo al archivo de recursos `rf.resource`, ejecute:  
  
```  
csc /linkresource:rf.resource in.cs  
```  
  
## Ejemplo  
 Para compilar `A.cs` en un archivo DLL, vincularlo a un archivo DLL nativo N.dll y colocar el resultado en la Caché global de ensamblados \(GAC\), ejecute lo siguiente.  En este ejemplo, A.dll y N.dll residen en la GAC.  
  
```  
csc /linkresource:N.dll /t:library A.cs  
gacutil -i A.dll  
```  
  
## Ejemplo  
 Este ejemplo hace lo mismo que el anterior, pero utiliza las opciones de Assembly Linker.  
  
```  
csc /t:module A.cs  
al /out:A.dll A.netmodule /link:N.dll   
gacutil -i A.dll  
```  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Al.exe \(Assembly Linker\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)   
 [Trabajar con ensamblados y la memoria caché global de ensamblados](../Topic/Working%20with%20Assemblies%20and%20the%20Global%20Assembly%20Cache.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)