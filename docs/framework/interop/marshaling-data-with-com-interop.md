---
title: "serialización de datos con la interoperabilidad COM"
ms.custom: 
ms.date: 09/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a2af80ddb558959171c255a61fae460729306e0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="marshaling-data-with-com-interop"></a>serialización de datos con la interoperabilidad COM
La interoperabilidad COM proporciona compatibilidad para usar objetos COM desde código administrado y para exponer objetos administrados en COM. La compatibilidad con el cálculo de referencias de datos desde y hacia COM es exhaustiva y el comportamiento del cálculo de referencias casi siempre es correcto.  
  
 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] incluye las siguientes herramientas de interoperabilidad COM:  
  
-   [Importador de la biblioteca de tipos (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), que convierte una biblioteca de tipos COM en un ensamblado de interoperabilidad. Desde este ensamblado, el servicio de serialización de interoperabilidad genera contenedores que realizan el cálculo de referencias de datos entre la memoria administrada y la no administrada.  
  
-   [Exportador de la biblioteca de tipos (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), que crea una biblioteca de tipos COM a partir un ensamblado y genera un contenedor que realiza la serialización durante las llamadas a métodos.  
  
 En las secciones siguientes se vinculan a temas que describen los procesos para personalizar los contenedores de interoperabilidad si puede (o debe) suministrar información adicional sobre tipos al contador de referencias.  
  
## <a name="in-this-section"></a>En esta sección  
[Cómo: crear contenedores manualmente](how-to-create-wrappers-manually.md)   
Describe cómo crear manualmente un contenedor COM en código fuente administrado. 
 
 [Cómo: Migrar código administrado DCOM a WCF](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 Describe cómo migrar código DCOM administrado a WCF para la solución más segura.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Tipos de datos COM](https://msdn.microsoft.com/en-us/library/sak564ww(v=vs.100).aspx)  
 Proporciona los tipos de datos administrados y no administrados correspondientes.  
  
 [Personalización de contenedores CCW](https://msdn.microsoft.com/en-us/library/3bwc828w(v=vs.100).aspx)  
 Describe cómo calcular explícitamente las referencias de tipos de datos mediante el <xref:System.Runtime.InteropServices.MarshalAsAttribute> atributos en tiempo de diseño.  
  
 [Personalización de contenedores RCW](https://msdn.microsoft.com/en-us/library/e753eftz(v=vs.100).aspx)  
 Describe cómo ajustar el comportamiento de serialización de tipos en un ensamblado de interoperabilidad y cómo definir tipos COM manualmente.  
  
 [Interoperabilidad COM avanzada](https://msdn.microsoft.com/en-us/library/bd9cdfyx(v=vs.100).aspx)  
 Proporciona vínculos a más información sobre la incorporación de componentes COM en una aplicación de .NET Framework.  
  
 [Resumen de la conversión de ensamblados en bibliotecas de tipos](https://msdn.microsoft.com/en-us/library/xk1120c3(v=vs.100).aspx)  
 Describe el proceso de conversión de la exportación de ensamblado a biblioteca de tipos.  
  
 [Resumen de la conversión de bibliotecas de tipos en ensamblados](https://msdn.microsoft.com/en-us/library/k83zzh38(v=vs.100).aspx)  
 Describe el proceso de conversión de la importación de biblioteca de tipos a ensamblado.  
  
 [Interoperar mediante tipos genéricos](https://msdn.microsoft.com/en-us/library/ms229590(v=vs.100).aspx)  
 Describe qué acciones se admiten al usar tipos genéricos para la interoperabilidad COM.
