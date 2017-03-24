---
title: Interoperabilidad COM en aplicaciones de .NET Framework (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: 15
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 308ee8e495efa9368ef55d781f6b6dc314db51ac
ms.lasthandoff: 03/13/2017

---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a>Interoperabilidad COM en aplicaciones .NET Framework (Visual Basic)
Si desea utilizar objetos COM y objetos de .NET Framework en la misma aplicación, debe resolver las diferencias en cómo los objetos existen en la memoria. Un objeto de .NET Framework se encuentra en la memoria administrada, la memoria controlada por common language runtime y se pueden mover en tiempo de ejecución según sea necesario. Un objeto COM se encuentra en la memoria no administrada y no se espera que se mueve a otra ubicación de memoria. [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]y el [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] proporcionan herramientas para controlar la interacción de estas administrado y componentes. Para obtener más información sobre el código administrado, consulte [Common Language Runtime](http://msdn.microsoft.com/library/059a624e-f7db-4134-ba9f-08b676050482).  
  
 Además de utilizar objetos COM en aplicaciones. NET, también puede utilizar [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] para desarrollar objetos accesibles desde código no administrado a través de COM.  
  
 Los vínculos en esta página proporcionan detalles sobre las interacciones entre objetos COM y .NET Framework.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)  
 Proporciona vínculos a temas que tratan sobre la interoperabilidad COM en Visual Basic, incluidos los objetos de COM, controles de ActiveX, archivos DLL para Win32, objetos administrados y herencia de objetos COM.  
  
 [Error de contenedor de interoperabilidad COM](https://docs.microsoft.com/cpp/misc/com-interop-wrapper-error)  
 Describe las opciones y las consecuencias si el sistema del proyecto no puede crear un contenedor de interoperabilidad COM para un componente concreto.  
  
 [Interoperación con código no administrado](https://msdn.microsoft.com/library/sd10k43k)  
 Describe algunos de los problemas de interacción entre código administrado y brevemente y proporciona vínculos a más información.  
  
 [Contenedores COM](http://msdn.microsoft.com/library/e56c485b-6b67-4345-8e66-fd21835a6092)  
 Describe contenedores RCW, que permiten al código administrado llamar a métodos COM, y los contenedores COM invocables, que permiten a los clientes COM llamar a métodos de objeto. NET.  
  
 [Interoperabilidad COM avanzada](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 Proporciona vínculos a temas sobre la interoperabilidad COM con respecto a contenedores, excepciones, herencia, subprocesos, eventos, conversiones y cálculo de referencias.  
  
 [Tlbimp.exe (importador de la biblioteca de tipos)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)  
 Describe la herramienta que se puede utilizar para convertir las definiciones de tipos encontradas en una biblioteca de tipos COM en las definiciones equivalentes en un ensamblado de common language runtime.
