---
title: serialización de datos con la interoperabilidad COM
ms.date: 09/07/2017
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d16f94e8b85a1bedb8b7791c2b7fcaf6d154ba1b
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833525"
---
# <a name="marshaling-data-with-com-interop"></a>serialización de datos con la interoperabilidad COM
La interoperabilidad COM proporciona compatibilidad para usar objetos COM desde código administrado y para exponer objetos administrados en COM. La compatibilidad con el cálculo de referencias de datos desde y hacia COM es exhaustiva y el comportamiento de serialización casi siempre es correcto.  
  
 El kit de desarrollo de Software (SDK) de Windows incluye las siguientes herramientas de interoperabilidad COM:  
  
- [Importador de la biblioteca de tipos (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), que convierte una biblioteca de tipos COM en un ensamblado de interoperabilidad. Desde este ensamblado, el servicio de cálculo de referencias de interoperabilidad genera contenedores que realizan el cálculo de referencias de datos entre la memoria administrada y la no administrada.  
  
- [Exportador de la biblioteca de tipos (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), que crea una biblioteca de tipos COM a partir un ensamblado y genera un contenedor que realiza la serialización durante las llamadas a métodos.  
  
 Las secciones siguientes se vinculan a los temas que describen los procesos para personalizar los contenedores de interoperabilidad si puede (o debe) suministrar información adicional sobre tipos al contador al serializador.  
  
## <a name="in-this-section"></a>En esta sección  
[Cómo: Crear contenedores de forma manual](how-to-create-wrappers-manually.md)   
Describe cómo crear manualmente un contenedor COM en código fuente administrado. 
 
 [Cómo: Migrar código administrado DCOM a WCF](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 Describe cómo migrar código DCOM administrado a WCF para obtener la solución más segura.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Tipos de datos COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))  
 Proporciona los tipos de datos administrados y no administrados correspondientes.  
  
 [Personalización de contenedores CCW](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))  
 Describe cómo serializar tipos de datos explícitamente mediante el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> en tiempo de diseño.  
  
 [Personalización de contenedores RCW](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))  
 Describe cómo ajustar el comportamiento de cálculo de referencias de tipos en un ensamblado de interoperabilidad y cómo definir tipos COM manualmente.  
  
 [Interoperabilidad COM avanzada](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))  
 Proporciona vínculos a más información sobre la incorporación de componentes COM en una aplicación de .NET Framework.  
  
 [Resumen de la conversión de ensamblados en bibliotecas de tipos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))  
 Describe el proceso de conversión de la exportación de ensamblado a biblioteca de tipos.  
  
 [Resumen de la conversión de bibliotecas de tipos en ensamblados](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))  
 Describe el proceso de conversión de la importación de biblioteca de tipos a ensamblado.  
  
 [Interoperar mediante tipos genéricos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))  
 Describe qué acciones se admiten al usar tipos genéricos para la interoperabilidad COM.
