---
title: serialización de datos con la interoperabilidad COM
description: Consulte los artículos que tratan de la serialización de datos con la interoperabilidad COM. Las herramientas Tlbimp.exe y Tlbexp.exe realizan conversiones entre una biblioteca de tipos COM y un ensamblado de interoperabilidad.
ms.date: 09/07/2017
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
ms.openlocfilehash: bcbd2c50fcbd9af3f2eead57ac2e26f8db0c6ad6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275949"
---
# <a name="marshaling-data-with-com-interop"></a>serialización de datos con la interoperabilidad COM

La interoperabilidad COM proporciona compatibilidad para usar objetos COM desde código administrado y para exponer objetos administrados en COM. La compatibilidad con el cálculo de referencias de datos desde y hacia COM es exhaustiva y el comportamiento de serialización casi siempre es correcto.  
  
 Windows SDK incluye las siguientes herramientas de interoperabilidad COM:  
  
- [Importador de la biblioteca de tipos (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md), que convierte una biblioteca de tipos COM en un ensamblado de interoperabilidad. Desde este ensamblado, el servicio de cálculo de referencias de interoperabilidad genera contenedores que realizan el cálculo de referencias de datos entre la memoria administrada y la no administrada.  
  
- [Exportador de la biblioteca de tipos (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md), que crea una biblioteca de tipos COM a partir un ensamblado y genera un contenedor que realiza la serialización durante las llamadas a métodos.  
  
 Las secciones siguientes se vinculan a los temas que describen los procesos para personalizar los contenedores de interoperabilidad si puede (o debe) suministrar información adicional sobre tipos al contador al serializador.  
  
## <a name="in-this-section"></a>En esta sección  

[Cómo: para la creación manual de contenedores](how-to-create-wrappers-manually.md) Describe cómo crear manualmente un contenedor COM en código fuente administrado.

 [Cómo: Migrar código administrado DCOM a WCF](how-to-migrate-managed-code-dcom-to-wcf.md)  
 Describe cómo migrar código DCOM administrado a WCF para obtener la solución más segura.  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Tipos de datos COM](/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))  
 Proporciona los tipos de datos administrados y no administrados correspondientes.  
  
 [Personalización de contenedores CCW](/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))  
 Describe cómo serializar tipos de datos explícitamente mediante el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> en tiempo de diseño.  
  
 [Personalización de contenedores RCW](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))  
 Describe cómo ajustar el comportamiento de cálculo de referencias de tipos en un ensamblado de interoperabilidad y cómo definir tipos COM manualmente.  
  
 [Interoperabilidad COM avanzada](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))  
 Proporciona vínculos a más información sobre la incorporación de componentes COM en una aplicación de .NET Framework.  
  
 [Resumen de la conversión de ensamblados en bibliotecas de tipos](/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))  
 Describe el proceso de conversión de la exportación de ensamblado a biblioteca de tipos.  
  
 [Resumen de la conversión de bibliotecas de tipos en ensamblados](/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))  
 Describe el proceso de conversión de la importación de biblioteca de tipos a ensamblado.  
  
 [Interoperar mediante tipos genéricos](/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))  
 Describe qué acciones se admiten al usar tipos genéricos para la interoperabilidad COM.
