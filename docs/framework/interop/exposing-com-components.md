---
title: Exponer componentes COM en .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26efd43a05252e657626063d7dd04b1020dace18
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="exposing-com-components-to-the-net-framework"></a>Exponer componentes COM en .NET Framework
En esta sección se resume el proceso necesario para exponer un componente COM existente a código administrado. Para obtener más detalles sobre cómo escribir servidores COM que se integren estrechamente con .NET Framework, vea [Consideraciones de diseño para interoperaciones](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689).  
  
 Los componentes COM existentes son recursos valiosos en código administrado como aplicaciones empresariales de nivel medio o funcionalidad aislada. Un componente ideal tiene un ensamblado de interoperabilidad primario y se ajusta totalmente a los estándares de programación impuestos por COM.  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a>Para exponer componentes COM en .NET Framework  
  
1.  [Importe una biblioteca de tipos como un ensamblado](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md).  
  
     Common Language Runtime requiere metadatos para todos los tipos, incluidos los tipos COM. Hay varias maneras de obtener un ensamblado que contiene tipos COM importados como metadatos.  
  
2.  [Cree tipos COM en código administrado](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).  
  
     Puede inspeccionar los tipos COM, activar instancias e invocar métodos en el objeto COM de la misma manera que lo hace para cualquier tipo administrado.  
  
3.  [Compile un proyecto de interoperabilidad](../../../docs/framework/interop/compiling-an-interop-project.md).  
  
     El [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] proporciona compiladores para varios lenguajes compatibles con Common Language Specification (CLS), incluidos [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# y C++.  
  
4.  [Implemente una aplicación de interoperabilidad](../../../docs/framework/interop/deploying-an-interop-application.md).  
  
     Las aplicaciones de interoperabilidad se implementan mejor como ensamblados firmados [con nombre seguro](../../../docs/framework/app-domains/strong-named-assemblies.md) en la caché global de ensamblados.  
  
## <a name="see-also"></a>Vea también  
 [Interoperating with Unmanaged Code](../../../docs/framework/interop/index.md) (Interoperar con código no administrado)  
 [Consideraciones de diseño para interoperaciones](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)  
 [Ejemplo de interoperabilidad COM: cliente .NET y servidor COM](../../../docs/framework/interop/com-interop-sample-net-client-and-com-server.md)  
 [Independencia del lenguaje y componentes independientes del lenguaje](../../../docs/standard/language-independence-and-language-independent-components.md)  
 [Gacutil.exe (Herramienta Caché global de ensamblados)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
