---
title: "Cómo: cargar y descargar ensamblados (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: bbc84236-04b6-4c1b-9672-52773f65a5dc
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 460d3a18fdee74c9b9c49ee465247b5b12d554d8
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-load-and-unload-assemblies-visual-basic"></a>Cómo: cargar y descargar ensamblados (Visual Basic)
Los ensamblados a los que hace referencia el programa se cargarán automáticamente en tiempo de compilación, pero también es posible cargar ensamblados específicos en el dominio de aplicación actual en tiempo de ejecución. Para obtener más información, consulte [Cómo: cargar ensamblados en un dominio de aplicación](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).  
  
 No existe ninguna forma de descargar un ensamblado individual sin descargar todos los dominios de aplicación que lo contienen. Aunque el ensamblado esté fuera de ámbito, el archivo de ensamblado actual permanecerá cargado hasta que se descarguen todos los dominios de aplicación que lo contienen.  
  
 Si desea descargar algunos ensamblados pero no otros, considere la posibilidad de crear un nuevo dominio de aplicación, ejecutar el código en el dominio y, a continuación, descargar ese dominio de aplicación. Para obtener más información, consulte [Cómo: descargar un dominio de aplicación](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a>Para cargar un ensamblado en un dominio de aplicación  
  
1.  Utilice uno de los métodos de carga varios contenidos en las clases <xref:System.AppDomain>y <xref:System.Reflection>.</xref:System.Reflection> </xref:System.AppDomain> Para obtener más información, consulte [Cómo: cargar ensamblados en un dominio de aplicación](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).  
  
### <a name="to-unload-an-application-domain"></a>Para descargar un dominio de aplicación  
  
1.  No existe ninguna forma de descargar un ensamblado individual sin descargar todos los dominios de aplicación que lo contienen. Utilice la `Unload` método <xref:System.AppDomain>para descargar los dominios de aplicación.</xref:System.AppDomain> Para obtener más información, consulte [Cómo: descargar un dominio de aplicación](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).  
  
## <a name="see-also"></a>Vea también  
 [Conceptos de programación](../../../../visual-basic/programming-guide/concepts/index.md)   
 [Ensamblados y caché Global de ensamblados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Cómo: cargar ensamblados en un dominio de aplicación](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)
