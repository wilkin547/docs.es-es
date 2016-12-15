---
title: "/keycontainer (C# Compiler Options) | Microsoft Docs"
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
  - "/keycontainer"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/keycontainer compiler option [C#]"
  - "keycontainer compiler option [C#]"
  - "-keycontainer compiler option [C#]"
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /keycontainer (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Especifica el nombre del contenedor de claves criptográficas.  
  
## Sintaxis  
  
```  
/keycontainer:string  
```  
  
## Argumentos  
 `string`  
 Nombre del contenedor de clave de nombre seguro.  
  
## Comentarios  
 Cuando se utiliza la opción **\/keycontainer**, el compilador crea un componente compartible insertando en el manifiesto del ensamblado la clave pública incluida en el contenedor especificado, y firma el ensamblado final con la clave privada.  Para generar un archivo de clave, escriba sn \- k `file` en la línea de comandos. sn \- i instala el par de claves en un contenedor.  
  
 Si se compila con la opción [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), el nombre del archivo de clave queda almacenado en el módulo y se incorpora al ensamblado al compilar este módulo como un ensamblado mediante [\/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 También puede especificar esta opción como un atributo personalizado \(<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName>\) en el código fuente de cualquier módulo de lenguaje intermedio de Microsoft \(MSIL\).  
  
 También puede pasar la información de cifrado al compilador mediante [\/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md).  Utilice [\/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) si desea agregar la clave pública al manifiesto del ensamblado pero prefiere retardar la firma del ensamblado hasta haberlo probado.  
  
 Para obtener más información, vea [Crear y utilizar ensamblados con nombre seguro](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) y [Retrasar la firma de un ensamblado](../Topic/Delay%20Signing%20an%20Assembly.md).  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Esta opción del compilador no está disponible en el entorno de desarrollo de Visual Studio.  
  
 Puede tener acceso a esta opción del compilador con <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)