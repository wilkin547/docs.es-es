---
title: "Exposing COM Components to the .NET Framework | Microsoft Docs"
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
  - "exposing COM components to .NET Framework"
  - "interoperation with unmanaged code, exposing COM components"
  - "COM interop, exposing COM components"
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Exposing COM Components to the .NET Framework
En esta sección se resume el proceso necesario para exponer un componente COM existente en el código administrado.  Para obtener información detallada acerca de la escritura de servidores COM estrechamente integrados con .NET Framework, vea [Consideraciones de diseño para interoperaciones](http://msdn.microsoft.com/es-es/b59637f6-fe35-40d6-ae72-901e7a707689).  
  
 Los componentes COM existentes son recursos muy valiosos en código administrado como aplicaciones empresariales de nivel medio o funcionalidad aislada.  Un componente ideal tiene un ensamblado de interoperabilidad primario y cumple rigurosamente los estándares de programación que impone COM.  
  
#### Para exponer componentes COM en .NET Framework  
  
1.  [Importe una biblioteca de tipos como un ensamblado](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md).  
  
     Common Language Runtime requiere metadatos para todos los tipos, incluidos los tipos COM.  Hay varias formas de obtener un ensamblado que contenga tipos COM importados como metadatos.  
  
2.  [Crear tipos COM en código administrado](http://msdn.microsoft.com/es-es/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).  
  
     Es posible inspeccionar tipos COM, activar instancias e invocar métodos en el objeto COM del mismo modo que se hace para cualquier tipo administrado.  
  
3.  [Compile un proyecto de interoperabilidad](../../../docs/framework/interop/compiling-an-interop-project.md).  
  
     [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] proporciona compiladores para varios lenguajes conformes a Common Language Specification \(CLS\), incluidos [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C\# y C\+\+.  
  
4.  [Implemente una aplicación interoperativa](../../../docs/framework/interop/deploying-an-interop-application.md).  
  
     La mejor forma de implementar aplicaciones interoperativas es hacerlo en forma de ensamblados firmados y con [nombre seguro](../../../docs/framework/app-domains/strong-named-assemblies.md) en la caché global de ensamblados.  
  
## Vea también  
 [Interoperating with Unmanaged Code](../../../docs/framework/interop/index.md)   
 [Design Considerations for Interoperation](http://msdn.microsoft.com/es-es/b59637f6-fe35-40d6-ae72-901e7a707689)   
 [COM Interop Sample: .NET Client and COM Server](../../../docs/framework/interop/com-interop-sample-net-client-and-com-server.md)   
 [Independencia del lenguaje y componentes independientes del lenguaje](../../../docs/standard/language-independence-and-language-independent-components.md)   
 [Gacutil.exe \(Global Assembly Cache Tool\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)