---
title: "/keyfile (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/keyfile"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/keyfile compiler option [C#]"
  - "-keyfile compiler option [C#]"
  - "keyfile compiler option [C#]"
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# /keyfile (C# Compiler Options)
Especifica el nombre de archivo que contiene la clave criptográfica.  
  
## Sintaxis  
  
```  
/keyfile:file  
```  
  
## Argumentos  
  
|Término|Definición|  
|-------------|----------------|  
|`file`|Nombre del archivo que contiene la clave de nombre seguro.|  
  
## Comentarios  
 Cuando se utiliza esta opción, el compilador inserta la clave pública del archivo especificado en el manifiesto del ensamblado y, a continuación, firma el último ensamblado con la clave privada.  Para generar un archivo de clave, escriba sn \-k `file` en la línea de comandos.  
  
 Si se compila con la opción **\/target:module**, el nombre del archivo de claves se mantiene en el módulo y se incorpora en el ensamblado que se crea al compilar un ensamblado con la opción [\/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 También puede pasar la información de cifrado al compilador mediante [\/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).  Utilice [\/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) para firmar el ensamblado de forma parcial.  
  
 Si se especifica tanto \/keyfile como \/keycontainer \(ya sea mediante una opción de línea de comandos o mediante un atributo personalizado\) en la misma compilación, el compilador probará primero el contenedor de clave.  Si el intento tiene éxito, el ensamblado se firmará con la información del contenedor de claves.  Si el compilador no encuentra el contenedor de clave, probará el archivo especificado con \/keyfile.  Si el intento tiene éxito, el ensamblado se firmará con la información contenida en el archivo de claves y la información de claves se instalará en el contenedor de claves \(similar a sn \-i\) de modo que en la siguiente compilación, el contenedor de claves será válido.  
  
 Tenga en cuenta que es posible que un archivo de claves contenga sólo la clave pública.  
  
 Para obtener más información, vea [Crear y utilizar ensamblados con nombre seguro](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) y [Retrasar la firma de un ensamblado](../Topic/Delay%20Signing%20an%20Assembly.md).  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Firma**.  
  
3.  Modifique la propiedad **Elija un archivo de clave de nombre seguro**.  
  
 Puede tener acceso mediante programación a esta opción del compilador con <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)