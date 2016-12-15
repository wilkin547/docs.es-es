---
title: "/lib (C# Compiler Options) | Microsoft Docs"
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
  - "/lib"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lib compiler option [C#]"
  - "-lib compiler option [C#]"
  - "/lib compiler option [C#]"
ms.assetid: b0efcc88-e8aa-4df4-a00b-8bdef70b7673
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /lib (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La opción **\/lib** especifica la ubicación de los ensamblados a los que se hace referencia mediante la opción [\/reference \(Import Metadata\)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md).  
  
## Sintaxis  
  
```  
/lib:dir1[,dir2]  
```  
  
## Argumentos  
 `dir1`  
 Directorio utilizado por el compilador para buscar un ensamblado al que se hace referencia si no lo encuentra en el directorio de trabajo actual \(el directorio desde el que se invoca al compilador\) o en el directorio del sistema de Common Language Runtime.  
  
 `dir2`  
 Uno o varios directorios adicionales para buscar las referencias a ensamblados.  Separe los nombres de directorio adicionales con una coma y sin espacio en blanco entre ellos.  
  
## Comentarios  
 El compilador busca referencias a ensamblados que no presentan la ruta completa en el siguiente orden:  
  
1.  Directorio actual de trabajo.  Es el directorio desde donde se invoca al compilador.  
  
2.  Directorio del sistema de Common Language Runtime.  
  
3.  Directorios especificados por **\/lib**.  
  
4.  Directorios especificados por la variable de entorno LIB.  
  
 Hay que utilizar **\/reference** para especificar una referencia a un ensamblado.  
  
 La opción **\/lib** es sumatoria; si se especifica más de una vez, anexa nuevos valores a los ya existentes.  
  
 Una alternativa al uso de **\/lib** consiste en copiar en el directorio de trabajo los ensamblados requeridos; esto permitirá pasar el nombre del ensamblado a **\/reference**.  A continuación, se pueden eliminar los ensamblados del directorio de trabajo.  Dado que en el manifiesto del ensamblado no se especifica la ruta al ensamblado dependiente, la aplicación puede iniciarse en el equipo de destino y desde allí buscará y utilizará el ensamblado en la caché global de ensamblados.  
  
 El hecho de que el compilador puede hacer referencia al ensamblado, no implica que Common Language Runtime pueda buscar y cargar el ensamblado en tiempo de ejecución.  Vea [Cómo el motor en tiempo de ejecución ubica ensamblados](../Topic/How%20the%20Runtime%20Locates%20Assemblies.md) para obtener los detalles sobre cómo busca el motor en tiempo de ejecución los ensamblados a los que se hace referencia.  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra el cuadro de diálogo **Páginas de propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Ruta de acceso de referencias**.  
  
3.  Modifique el contenido del cuadro de lista.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>.  
  
## Ejemplo  
 Para compilar t2.cs con el fin de crear un archivo .exe.  El compilador busca referencias a ensamblados en el directorio de trabajo y en el directorio raíz de la unidad C.  
  
```  
csc /lib:c:\ /reference:t2.dll t2.cs  
```  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)