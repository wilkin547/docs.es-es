---
title: "/baseaddress (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/dllbase"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "baseaddress compiler option [C#]"
  - "/baseaddress compiler option [C#]"
  - "-baseaddress compiler option [C#]"
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /baseaddress (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La opción **\/baseaddress** permite especificar la dirección base preferida para cargar un archivo DLL.  Para obtener más información sobre cuándo y por qué utilizar esta opción, vea [Mejora de tiempo de inicio de la aplicación](http://go.microsoft.com/fwlink/?LinkId=107043) y [WebLog de Larry Osterman](http://go.microsoft.com/fwlink/?LinkId=107044).  
  
## Sintaxis  
  
```  
/baseaddress:address  
```  
  
## Argumentos  
 `address`  
 Dirección base para el archivo DLL.  Esta dirección puede especificarse como número decimal, hexadecimal u octal.  
  
## Comentarios  
 La dirección base predeterminada de un archivo DLL la establece Common Language Runtime de .NET Framework.  
  
 Hay que tener en cuenta que se redondeará la palabra de orden inferior de esta dirección.  Por ejemplo, si se especifica 0x11110001, quedará redondeada como 0x11110000.  
  
 Para completar el proceso de firma de un archivo DLL, utilice SN.EXE con la opción \-R.  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Compilar**.  
  
3.  Haga clic en el botón **Avanzada**.  
  
4.  Modifique la propiedad **Dirección base del archivo DLL**.  
  
     Para establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.  
  
## Vea también  
 <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=fullName>   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)