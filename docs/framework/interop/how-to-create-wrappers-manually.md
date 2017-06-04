---
title: "How to: Create Wrappers Manually | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "wrappers, creating manually"
ms.assetid: cc2a70d8-6a58-4071-a8cf-ce28c018c09b
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Create Wrappers Manually
Si decide declarar manualmente los tipos COM en código fuente administrado, lo mejor es empezar con un archivo o una biblioteca de tipos existente del Lenguaje de definición de interfaz \(IDL\).  Cuando no tiene el archivo IDL o no puede generar un archivo de biblioteca de tipos, puede simular los tipos COM si crea declaraciones administradas y exporta el ensamblado resultante a una biblioteca de tipos.  
  
### Para simular tipos COM a partir de código fuente administrado  
  
1.  Declare los tipos en un lenguaje conforme a CLS \(Common Language Specification\) y compile el archivo.  
  
2.  Exporte el ensamblado que contiene los tipos con la [herramienta Exportador de la biblioteca de tipos \(Tlbexp.exe\)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).  
  
3.  Utilice la biblioteca de tipos COM exportada como base para declarar tipos administrados orientados a COM.  
  
### Para crear un contenedor invocable en tiempo de ejecución \(RCW\)  
  
1.  Suponiendo que tiene un archivo IDL o un archivo de biblioteca de tipos, decida qué clases e interfaces desea incluir en el RCW personalizado.  Puede excluir cualquier tipo que no piense utilizar directa o indirectamente en su aplicación.  
  
2.  Cree un archivo código fuente en un lenguaje conforme a CLS y declare los tipos.  Vea [Resumen de la conversión de bibliotecas de tipos en ensamblados](http://msdn.microsoft.com/es-es/bf3f90c5-4770-4ab8-895c-3ba1055cc958) para obtener una descripción completa del proceso de conversión de importación.  Cuando se crea un RCW personalizado, se realiza manualmente la conversión de tipos proporcionada por el [Importador de la biblioteca de tipos \(Tlbimp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md).  El ejemplo de la siguiente sección muestra los tipos de un IDL o un archivo de biblioteca de tipos y sus tipos correspondientes en código de C\#.  
  
3.  Una vez completadas las declaraciones, compile el archivo de la misma forma que compila cualquier otro código fuente administrado.  
  
4.  Como ocurre con los tipos importados con Tlbimp.exe, algunos requieren información adicional, que puede agregar directamente al código.  Para obtener más detalles, vea [Editar un ensamblado de interoperabilidad](http://msdn.microsoft.com/es-es/16aacb20-2269-42bf-a812-b6a7df17e277).  
  
## Ejemplo  
 En el siguiente código se muestra un ejemplo de la interfaz `ISATest` y la clase `SATest` en IDL, y los tipos correspondientes en código fuente de C\#.  
  
 **Archivo IDL o de biblioteca de tipos**  
  
```  
 [  
object,  
uuid(40A8C65D-2448-447A-B786-64682CBEF133),  
dual,  
helpstring("ISATest Interface"),  
pointer_default(unique)  
 ]  
interface ISATest : IDispatch  
 {  
[id(1), helpstring("method InSArray")]   
HRESULT InSArray([in] SAFEARRAY(int) *ppsa, [out,retval] int *pSum);  
 };  
 [  
uuid(116CCA1E-7E39-4515-9849-90790DA6431E),  
helpstring("SATest Class")  
 ]  
coclass SATest  
 {  
  [default] interface ISATest;  
 };  
```  
  
 **Contenedor en código fuente administrado**  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
using System.Runtime.CompilerServices;  
  
[assembly:Guid("E4A992B8-6F5C-442C-96E7-C4778924C753")]  
[assembly:ImportedFromTypeLib("SAServerLib")]  
namespace SAServer  
{  
 [ComImport]  
 [Guid("40A8C65D-2448-447A-B786-64682CBEF133")]  
 [TypeLibType(TypeLibTypeFlags.FLicensed)]  
 public interface ISATest  
 {  
  [DispId(1)]  
  //[MethodImpl(MethodImplOptions.InternalCall,  
  // MethodCodeType=MethodCodeType.Runtime)]  
  int InSArray( [MarshalAs(UnmanagedType.SafeArray,  
      SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }   
 [ComImport]  
 [Guid("116CCA1E-7E39-4515-9849-90790DA6431E")]  
 [ClassInterface(ClassInterfaceType.None)]   
 [TypeLibType(TypeLibTypeFlags.FCanCreate)]  
 public class SATest : ISATest   
 {  
  [DispId(1)]  
  [MethodImpl(MethodImplOptions.InternalCall,   
  MethodCodeType=MethodCodeType.Runtime)]  
  extern int ISATest.InSArray( [MarshalAs(UnmanagedType.SafeArray,   
  SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }  
}  
```  
  
## Vea también  
 [Customizing Runtime Callable Wrappers](http://msdn.microsoft.com/es-es/4652beaf-77d0-4f37-9687-ca193288c0be)   
 [COM Data Types](http://msdn.microsoft.com/es-es/f93ae35d-a416-4218-8700-c8218cc90061)   
 [How to: Edit Interop Assemblies](http://msdn.microsoft.com/es-es/16aacb20-2269-42bf-a812-b6a7df17e277)   
 [Type Library to Assembly Conversion Summary](http://msdn.microsoft.com/es-es/bf3f90c5-4770-4ab8-895c-3ba1055cc958)   
 [Tlbimp.exe \(Type Library Importer\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)   
 [Tlbexp.exe \(Type Library Exporter\)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)