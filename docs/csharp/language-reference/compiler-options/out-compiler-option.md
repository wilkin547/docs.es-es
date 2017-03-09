---
title: "/out (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/out"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/out compiler option [C#]"
  - "out compiler option [C#]"
  - "-out compiler option [C#]"
ms.assetid: 70d91d01-7bd2-4aea-ba8b-4e9807e9caa5
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# /out (C# Compiler Options)
La opción **\/out** especifica el nombre del archivo de salida.  
  
## Sintaxis  
  
```  
/out:filename  
```  
  
## Argumentos  
 `filename`  
 Nombre del archivo de salida creado por el compilador.  
  
## Comentarios  
 En la línea de comandos, es posible especificar varios archivos de salida de una compilación.  El compilador espera encontrar al menos un archivo de código fuente después de la opción **\/out**.  Posteriormente, todos los archivos de código fuente se compilarán en el archivo de salida especificado por la opción **\/out**.  
  
 Hay que especificar el nombre completo y la extensión del archivo que se desea crear.  
  
 Si no se especifica el nombre del archivo de salida:  
  
-   Un archivo .exe toma el nombre del archivo de código fuente que contiene el método **Main**.  
  
-   Un archivo .dll o un .netmodule tendrá el nombre del primer archivo de código fuente.  
  
 Un archivo de código fuente utilizado para compilar un archivo de salida no puede utilizarse para compilar otro archivo de este tipo en la misma compilación.  
  
 Cuando se producen varios archivos de salida en una compilación de línea de comandos, recuerde que sólo uno de los archivos de salida puede ser un ensamblado y que sólo el primero que haya especificado \(ya sea implícita o explícitamente con **\/out**\) puede ser el ensamblado.  
  
 Todos los módulos que se produzcan como parte de una compilación se convierten en archivos asociados a cualquier ensamblado que también se haya producido en la compilación.  Utilice [ildasm.exe](../Topic/Ildasm.exe%20\(IL%20Disassembler\).md) para ver el manifiesto del ensamblado y los archivos asociados.  
  
 Es obligatorio utilizar la opción \/out del compilador que un archivo exe sea el destino de un ensamblado de confianza.  Para obtener más información, vea [Ensamblados de confianza](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Aplicación**.  
  
3.  Modifique la propiedad **Nombre del ensamblado**.  
  
     Para establecer esta opción del compilador mediante programación: <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> es una propiedad de sólo lectura que se determina a partir de una combinación del tipo de proyecto \(ejecutable, biblioteca, etc.\) y el nombre del ensamblado.  Es necesario modificar una de estas propiedades o ambas para establecer el nombre del archivo de salida.  
  
## Ejemplo  
 Para compilar `t.cs` y crear el archivo de salida `t.exe`, y para generar `t2.cs` y crear el archivo de salida del módulo `mymodule.netmodule`, ejecute:  
  
```  
csc t.cs /out:mymodule.netmodule /target:module t2.cs  
```  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Ensamblados de confianza](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)