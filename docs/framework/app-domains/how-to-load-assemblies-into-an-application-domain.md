---
title: Procedimiento para cargar ensamblados en un dominio de aplicación
description: Aprenda a cargar ensamblados en un dominio de aplicación en .NET. El método recomendado consiste en usar el método de carga estático (o compartido) de System.Reflection.Assembly.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, loading assemblies
- loading assemblies
ms.assetid: 1432aa2d-bd83-4346-bf3b-a1b7920e2aa9
ms.openlocfilehash: cc37b5b5c64a65655d06418d08a66231577a5bad
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271491"
---
# <a name="how-to-load-assemblies-into-an-application-domain"></a>Procedimiento para cargar ensamblados en un dominio de aplicación

Existen numerosas formas de cargar un ensamblado en un dominio de aplicación. El método recomendado consiste en usar el método <xref:System.Reflection.Assembly.Load%2A>`static` (`Shared` en Visual Basic) de la clase <xref:System.Reflection.Assembly?displayProperty=nameWithType>. A continuación se indican otras formas de cargar los ensamblados:  
  
- El método <xref:System.Reflection.Assembly.LoadFrom%2A> de la clase <xref:System.Reflection.Assembly> carga un ensamblado a partir de la ubicación del archivo correspondiente. La carga de ensamblados mediante este método usa un contexto de carga distinto.  
  
- Los métodos <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> y <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> cargan un ensamblado en el contexto de solo reflexión. Los ensamblados cargados en este contexto pueden examinarse, pero no ejecutarse, lo que permite examinar los ensamblados que tienen como destino otras plataformas. Vea [Cómo: Cargar ensamblados en el contexto de solo reflexión](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
> [!NOTE]
> El contexto de solo reflexión es nuevo en la versión 2.0 de .NET Framework.  
  
- Los métodos como <xref:System.AppDomain.CreateInstance%2A> y <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> de la clase <xref:System.AppDomain> pueden cargar ensamblados en un dominio de aplicación.  
  
- El método <xref:System.Type.GetType%2A> de la clase <xref:System.Type> puede cargar ensamblados.  
  
- El método <xref:System.AppDomain.Load%2A> de la clase <xref:System.AppDomain?displayProperty=nameWithType> puede cargar ensamblados, pero se usa principalmente para la interoperabilidad COM. No se debe usar para cargar ensamblados en un dominio de aplicación que no sea el dominio de aplicación desde el que se llama.  
  
> [!NOTE]
> A partir de la versión 2.0 de .NET Framework, el tiempo de ejecución no cargará ningún ensamblado compilado con una versión de .NET Framework que tenga un número de versión superior al tiempo de ejecución cargado actualmente. Esto se aplica a la combinación de los componentes principal y secundario del número de versión.  
  
 Puede especificar cómo se comparte entre los dominios de aplicación el código compilado Just-In-Time (JIT) de los ensamblados cargados. Para obtener más información, consulte [Dominios de aplicación y ensamblados](application-domains.md#application-domains-and-assemblies).  
  
## <a name="example"></a>Ejemplo  

 El siguiente código carga un ensamblado llamado "example.exe" o "example.dll" en el dominio de aplicación actual, obtiene del ensamblado un tipo llamado `Example`, obtiene un método sin parámetros llamado `MethodA` para dicho tipo y lo ejecuta. Para obtener una descripción completa sobre cómo obtener información de un ensamblado cargado, consulte [Dynamically Loading and Using Types](../reflection-and-codedom/dynamically-loading-and-using-types.md) (Cargar y usar tipos dinámicamente).  
  
 [!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)]
 [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)]
 [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>
- [Programar con dominios de aplicación](application-domains.md#programming-with-application-domains)
- [Reflexión](../reflection-and-codedom/reflection.md)
- [Utilizar dominios de aplicación](use.md)
- [Cómo: Cargar ensamblados en el contexto de solo reflexión](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)
- [Dominios de aplicación y ensamblados](application-domains.md#application-domains-and-assemblies)
