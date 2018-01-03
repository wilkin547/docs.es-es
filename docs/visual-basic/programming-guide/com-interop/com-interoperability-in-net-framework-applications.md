---
title: Interoperabilidad COM en aplicaciones .NET Framework (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0c84143e22f33f572447c50e33559a52469b181a
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a>Interoperabilidad COM en aplicaciones .NET Framework (Visual Basic)
Si desea utilizar objetos COM y objetos de .NET Framework en la misma aplicación, debe resolver las diferencias en cómo los objetos existen en la memoria. Un objeto de .NET Framework se encuentra en la memoria administrada, la memoria controlada por common language runtime y se pueden mover en tiempo de ejecución según sea necesario. Un objeto COM se encuentra en la memoria no administrada y no se prevé que se mueva a otra ubicación de memoria. [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]y el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] proporcionan herramientas para controlar la interacción de estos administrados y componentes. Para obtener más información sobre el código administrado, consulte [Common Language Runtime](../../../standard/clr.md).  
  
 Además de usar objetos COM en aplicaciones. NET, también puede usar [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] para desarrollar objetos accesibles desde código no administrado a través de COM.  
  
 Los vínculos en esta página proporcionan detalles sobre las interacciones entre objetos COM y .NET Framework.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)  
 Proporciona vínculos a temas que tratan sobre la interoperabilidad COM en Visual Basic, incluidos objetos de COM, los controles de ActiveX, archivos DLL para Win32, los objetos administrados y herencia de objetos COM.  
  
 [Error de contenedor de interoperabilidad COM](/cpp/misc/com-interop-wrapper-error)  
 Describe las opciones y las consecuencias si el sistema del proyecto no puede crear un contenedor de interoperabilidad COM para un componente determinado.  
  
 [Interoperating with Unmanaged Code](../../../framework/interop/index.md) (Interoperar con código no administrado)  
 Describe algunos de los problemas de interacción entre código administrado y brevemente y proporciona vínculos a más información.  
  
 [Contenedores COM](../../../framework/interop/com-wrappers.md)  
 Describe contenedores invocables en tiempo de ejecución, lo que permite al código administrado llamar a métodos COM, y los contenedores CCW, que permiten a los clientes COM llamar a métodos de objeto. NET.  
  
 [Interoperabilidad COM avanzada](../../../framework/interop/index.md)  
 Proporciona vínculos a temas que tratan sobre la interoperabilidad COM con respecto a los contenedores, excepciones, herencia, subprocesos, eventos, conversiones y el cálculo de referencias.  
  
 [TlbImp.exe (Importador de la biblioteca de tipos)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 Describe la herramienta que puede usar para convertir las definiciones de tipos encontradas en una biblioteca de tipos COM en las definiciones equivalentes en un ensamblado de common language runtime.
