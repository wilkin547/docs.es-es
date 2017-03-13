---
title: "/link (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/l compiler option [C#]"
  - "/link compiler option [C#]"
  - "-l compiler option [C#]"
  - "EmbedInteropTypes"
  - "l compiler option [C#]"
  - "embed interop types [COM Interop]"
  - "-link compiler option [C#]"
  - "link compiler option [C#]"
ms.assetid: 00da70c6-9ea1-43c2-86f2-aa7f26c03475
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# /link (C# Compiler Options)
Hace que el compilador facilite la información de tipos COM presente en los ensamblados especificados al proyecto que se compila actualmente.  
  
## Sintaxis  
  
```  
/link:fileList  
// -or-  
/l:fileList  
```  
  
## Argumentos  
 `fileList`  
 Obligatorio.  Lista delimitada por comas de nombres de archivos de ensamblado.  Si el nombre de archivo contiene un espacio, incluya el nombre entre comillas.  
  
## Comentarios  
 La opción `/link` permite implementar una aplicación que contiene información de tipos incrustada.  La aplicación puede entonces usar los tipos de un ensamblado del runtime que implementan la información de tipos incrustada sin necesidad de una referencia al ensamblado del runtime.  Si se publican varias versiones del ensamblado del runtime, la aplicación que contiene la información de tipos incrustada puede funcionar con las diferentes versiones sin que sea necesario volver a compilarla.  Para obtener un ejemplo, vea [Tutorial: Incrustar los tipos de los ensamblados administrados](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
 La opción `/link` resulta especialmente útil cuando se trabaja con interoperabilidad COM.  Puede incrustar tipos COM para que la aplicación ya no requiera un ensamblado de interoperabilidad primario \(PIA\) en el equipo de destino.  La opción `/link` indica al compilador que incruste la información de tipos COM del ensamblado de interoperabilidad al que se hace referencia en el código compilado resultante.  El valor de CLSID \(GUID\) identifica el tipo COM.  Como resultado, la aplicación se puede ejecutar en un equipo de destino que tenga instalados los mismos tipos COM con los mismos valores de CLSID.  Las aplicaciones que automatizan Microsoft Office son un buen ejemplo.  Dado que las aplicaciones como Office suelen mantener el mismo valor de CLSID en sus distintas versiones, la aplicación puede usar los tipos COM a los que se hace referencia siempre que .NET Framework 4 o posterior se haya instalado en el equipo de destino y la aplicación use los métodos, las propiedades o los eventos incluidos en dichos tipos COM.  
  
 La opción `/link` incrusta solamente interfaces, estructuras y delegados.  No se admite la incrustación de clases COM.  
  
> [!NOTE]
>  Al crear una instancia de un tipo COM incrustado en el código, deberá crear dicha instancia con la interfaz adecuada.  Si se intenta crear una instancia de un tipo COM incrustado con el elemento Coclass se produce un error.  
  
 Para establecer la opción `/link` en [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)], agregue una referencia de ensamblado y establezca la propiedad `Embed Interop Types` en **true**.  El valor predeterminado de la propiedad `Embed Interop Types` es **false**.  
  
 Si se establece un vínculo con un ensamblado COM \(Ensamblado A\) que hace referencia a otro ensamblado COM \(Ensamblado B\), deberá establecer también un vínculo con el Ensamblado B si se da alguna de estas condiciones:  
  
-   Un tipo utilizado en el Ensamblado A hereda de un tipo o implementa una interfaz del Ensamblado B.  
  
-   Se invoca un campo, una propiedad, un evento o un método que tiene un tipo de valor devuelto o un tipo de parámetro del Ensamblado B.  
  
 Al igual que la opción del compilador [\/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md), la opción del compilador `/link` usa el archivo de respuesta Csc.rsp, que hace referencia a los ensamblados de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] que se usan con frecuencia.  Use la opción del compilador [\/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) si no desea que el compilador use el archivo Csc.rsp.  
  
 La forma corta de `/link` es `/l`.  
  
## Tipos incrustados y genéricos  
 En las secciones siguientes se describen las limitaciones al usar tipos genéricos en las aplicaciones que incrustan tipos de interoperabilidad.  
  
### Interfaces genéricas  
 No se pueden usar interfaces genéricas que se incrustan desde un ensamblado de interoperabilidad.  Esta implementación se muestra en el ejemplo siguiente.  
  
 [!code-cs[VbLinkCompilerCS#1](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_1.cs)]  
  
### Tipos con parámetros genéricos  
 Los tipos que tienen un parámetro genérico cuyo tipo se incrusta desde un ensamblado de interoperabilidad no se pueden usar si dicho tipo pertenece a un ensamblado externo.  Esta restricción no se aplica a las interfaces.  Por ejemplo, considere la interfaz <xref:Microsoft.Office.Interop.Excel.Range> que se define en el ensamblado <xref:Microsoft.Office.Interop.Excel>.  Si una biblioteca incrusta tipos de interoperabilidad del ensamblado <xref:Microsoft.Office.Interop.Excel> y expone un método que devuelve un tipo genérico con un parámetro cuyo tipo es la interfaz <xref:Microsoft.Office.Interop.Excel.Range>, ese método debe devolver una interfaz genérica, como se muestra en el ejemplo de código siguiente.  
  
 [!code-cs[VbLinkCompilerCS#2](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_2.cs)]  
[!code-cs[VbLinkCompilerCS#3](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_3.cs)]  
[!code-cs[VbLinkCompilerCS#4](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_4.cs)]  
  
 En el ejemplo siguiente, el código de cliente puede llamar al método que devuelve la interfaz genérica <xref:System.Collections.IList> sin errores.  
  
 [!code-cs[VbLinkCompilerCS#5](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_5.cs)]  
  
## Ejemplo  
 El código siguiente compila el archivo de código fuente `OfficeApp.cs` y los ensamblados de referencia de `COMData1.dll` y `COMData2.dll` para generar `OfficeApp.exe`.  
  
```c#  
csc /link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.cs  
```  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Tutorial: Incrustar los tipos de los ensamblados administrados](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [\/reference \(Import Metadata\)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)   
 [\/noconfig \(Ignore csc.rsp\)](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)   
 [Command\-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [Información general sobre interoperabilidad](../../../csharp/programming-guide/interop/interoperability-overview.md)