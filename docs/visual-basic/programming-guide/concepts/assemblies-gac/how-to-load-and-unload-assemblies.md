---
title: Filtrar Cargar y descargar ensamblados (Visual Basic)
ms.date: 07/20/2015
ms.assetid: bbc84236-04b6-4c1b-9672-52773f65a5dc
ms.openlocfilehash: 07c8370d7aeb5171f991ddf24bf473f787408f2d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838773"
---
# <a name="how-to-load-and-unload-assemblies-visual-basic"></a>Filtrar Cargar y descargar ensamblados (Visual Basic)
Los ensamblados a los que hace referencia el programa se cargarán automáticamente en tiempo de compilación, pero también es posible cargar ensamblados específicos en el dominio de aplicación actual en tiempo de ejecución. Para obtener más información, vea [Cómo: Cargar ensamblados en un dominio de aplicación](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).  
  
 No existe ninguna forma de descargar un ensamblado individual sin descargar todos los dominios de aplicación que lo contienen. Aunque el ensamblado esté fuera de ámbito, el archivo de ensamblado actual permanecerá cargado hasta que se descarguen todos los dominios de aplicación que lo contienen.  
  
 Si desea descargar algunos ensamblados pero no otros, considere la posibilidad de crear un nuevo dominio de aplicación, ejecutar el código en el dominio y, a continuación, descargar ese dominio de aplicación. Para obtener más información, vea [Cómo: Descargar un dominio de aplicación](../../../../framework/app-domains/how-to-unload-an-application-domain.md).  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a>Para cargar un ensamblado en un dominio de aplicación  
  
1.  Utilice uno de los diversos métodos de carga de las clases <xref:System.AppDomain> y <xref:System.Reflection>. Para obtener más información, vea [Cómo: Cargar ensamblados en un dominio de aplicación](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).  
  
### <a name="to-unload-an-application-domain"></a>Para descargar un dominio de aplicación  
  
1.  No existe ninguna forma de descargar un ensamblado individual sin descargar todos los dominios de aplicación que lo contienen. Utilice el método `Unload` de <xref:System.AppDomain> para descargar los dominios de aplicación. Para obtener más información, vea [Cómo: Descargar un dominio de aplicación](../../../../framework/app-domains/how-to-unload-an-application-domain.md).  
  
## <a name="see-also"></a>Vea también

- [Conceptos de programación](../../../../visual-basic/programming-guide/concepts/index.md)
- [Ensamblados de .NET](../../../../standard/assembly/index.md)
- [Cómo: Cargar ensamblados en un dominio de aplicación](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
