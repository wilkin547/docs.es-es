---
title: "Cómo: Cargar y descargar ensamblados (C#) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 8efd5a9ccfedbea401b0c95d443fe8cdb6ea6c32
ms.contentlocale: es-es
ms.lasthandoff: 05/10/2017

---
# <a name="how-to-load-and-unload-assemblies-c"></a>Cómo: Cargar y descargar ensamblados (C#)
Los ensamblados a los que hace referencia el programa se cargarán automáticamente en tiempo de compilación, pero también es posible cargar ensamblados específicos en el dominio de aplicación actual en tiempo de ejecución. Para obtener más información, vea [Cómo: Cargar ensamblados en un dominio de aplicación](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).  
  
 No existe ninguna forma de descargar un ensamblado individual sin descargar todos los dominios de aplicación que lo contienen. Aunque el ensamblado esté fuera de ámbito, el archivo de ensamblado actual permanecerá cargado hasta que se descarguen todos los dominios de aplicación que lo contienen.  
  
 Si desea descargar algunos ensamblados pero no otros, considere la posibilidad de crear un nuevo dominio de aplicación, ejecutar el código en el dominio y, a continuación, descargar ese dominio de aplicación. Para obtener más información, vea [Cómo: Descargar un dominio de aplicación](../../../../framework/app-domains/how-to-unload-an-application-domain.md).  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a>Para cargar un ensamblado en un dominio de aplicación  
  
1.  Utilice uno de los diversos métodos de carga de las clases <xref:System.AppDomain> y <xref:System.Reflection>. Para obtener más información, vea [Cómo: Cargar ensamblados en un dominio de aplicación](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).  
  
### <a name="to-unload-an-application-domain"></a>Para descargar un dominio de aplicación  
  
1.  No existe ninguna forma de descargar un ensamblado individual sin descargar todos los dominios de aplicación que lo contienen. Utilice el método `Unload` de <xref:System.AppDomain> para descargar los dominios de aplicación. Para obtener más información, vea [Cómo: Descargar un dominio de aplicación](../../../../framework/app-domains/how-to-unload-an-application-domain.md).  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../../csharp/programming-guide/index.md)   
 [Ensamblados y caché global de ensamblados (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)   
 [Cómo: Cargar ensamblados en un dominio de aplicación](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
