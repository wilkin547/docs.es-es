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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 15905b2c23320b57e5797d6084ce48cfc526ed7d
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-load-and-unload-assemblies-c"></a>Cómo: Cargar y descargar ensamblados (C#)
Los ensamblados a los que hace referencia el programa se cargarán automáticamente en tiempo de compilación, pero también es posible cargar ensamblados específicos en el dominio de aplicación actual en tiempo de ejecución. Para obtener más información, vea [Cómo: Cargar ensamblados en un dominio de aplicación](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).  
  
 No existe ninguna forma de descargar un ensamblado individual sin descargar todos los dominios de aplicación que lo contienen. Aunque el ensamblado esté fuera de ámbito, el archivo de ensamblado actual permanecerá cargado hasta que se descarguen todos los dominios de aplicación que lo contienen.  
  
 Si desea descargar algunos ensamblados pero no otros, considere la posibilidad de crear un nuevo dominio de aplicación, ejecutar el código en el dominio y, a continuación, descargar ese dominio de aplicación. Para obtener más información, vea [Cómo: Descargar un dominio de aplicación](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a>Para cargar un ensamblado en un dominio de aplicación  
  
1.  Use uno de los diversos métodos de carga contenidos en las clases <xref:System.AppDomain> y <xref:System.Reflection>. Para obtener más información, vea [Cómo: Cargar ensamblados en un dominio de aplicación](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).  
  
### <a name="to-unload-an-application-domain"></a>Para descargar un dominio de aplicación  
  
1.  No existe ninguna forma de descargar un ensamblado individual sin descargar todos los dominios de aplicación que lo contienen. Use el método `Unload` de <xref:System.AppDomain> para descargar los dominios de aplicación. Para obtener más información, vea [Cómo: Descargar un dominio de aplicación](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../../csharp/programming-guide/index.md)   
 [Ensamblados y caché global de ensamblados (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)   
 [Cómo: Cargar ensamblados en un dominio de aplicación](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)
