---
title: "/resource (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/resource"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-resource compiler option [C#]"
  - "/resource compiler option [C#]"
  - "-res compiler option [C#]"
  - "/res compiler option [C#]"
  - "res compiler option [C#]"
  - "resource compiler option [C#]"
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# /resource (C# Compiler Options)
Incrusta el recurso especificado en el archivo de salida.  
  
## Sintaxis  
  
```  
/resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## Argumentos  
 `filename`  
 Archivo de recursos de .NET Framework que se desea incrustar en el archivo de salida.  
  
 `identifier` \(opcional\)  
 Nombre lógico del recurso; nombre que se usa para cargar el recurso.   El valor predeterminado es el nombre del archivo.  
  
 `accessibility-modifier` \(opcional\)  
 Accesibilidad del recurso: pública o privada.  El valor predeterminado es que sea pública.  
  
## Comentarios  
 Use la opción [\/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) para vincular un recurso a un ensamblado y no incluir el archivo de recursos en el archivo de salida.  
  
 De forma predeterminada, los recursos son públicos en el ensamblado cuando se crean mediante el compilador de C\#.   Para que sean privados, especifique  el modificador de accesibilidad `private`.  No se permite ninguna otra accesibilidad distinta de `public` o `private`.  
  
 Si `filename` es un archivo de recursos de .NET Framework creado, por ejemplo, con [Resgen.exe](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) o en el entorno de desarrollo, se puede obtener acceso a él con miembros del espacio de nombres <xref:System.Resources>.  Para obtener más información, vea <xref:System.Resources.ResourceManager?displayProperty=fullName>.  Para todos los demás recursos, utilice los métodos `GetManifestResource`\* de la clase <xref:System.Reflection.Assembly> para obtener acceso al recurso en tiempo de ejecución.  
  
 **\/res** es la forma abreviada de **\/resource**.  
  
 El orden de los recursos en el archivo de salida se determina a partir del orden especificado en la línea de comandos.  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Agregue un archivo de recursos al proyecto.  
  
2.  En el **Explorador de soluciones**, seleccione el archivo que desea incrustar.  
  
3.  Seleccione **Acción de compilación** para el archivo en la ventana **Propiedades**.  
  
4.  Establezca el valor de **Acción de compilación** en **Recurso incrustado**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.FileProperties2.BuildAction%2A>.  
  
## Ejemplo  
 Para compilar `in.cs` y asociar el archivo de recursos `rf.resource`, ejecute:  
  
```  
csc /resource:rf.resource in.cs  
```  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)