---
title: serialización de datos con la interoperabilidad COM
ms.date: 09/07/2017
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0d94223223568efe921af3a340815a966cc6c6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33388360"
---
# <a name="marshaling-data-with-com-interop"></a>serialización de datos con la interoperabilidad COM
La interoperabilidad COM proporciona compatibilidad para usar objetos COM desde código administrado y para exponer objetos administrados en COM. La compatibilidad con el cálculo de referencias de datos desde y hacia COM es exhaustiva y el comportamiento del cálculo de referencias casi siempre es correcto.  
  
 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] incluye las siguientes herramientas de interoperabilidad COM:  
  
-   [Importador de la biblioteca de tipos (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), que convierte una biblioteca de tipos COM en un ensamblado de interoperabilidad. Desde este ensamblado, el servicio de serialización de interoperabilidad genera contenedores que realizan el cálculo de referencias de datos entre la memoria administrada y la no administrada.  
  
-   [Exportador de la biblioteca de tipos (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), que crea una biblioteca de tipos COM a partir un ensamblado y genera un contenedor que realiza la serialización durante las llamadas a métodos.  
  
 Las secciones siguientes se vinculan a los temas que describen los procesos para personalizar los contenedores de interoperabilidad si puede (o debe) suministrar información adicional sobre tipos al contador al serializador.  
  
## <a name="in-this-section"></a>En esta sección  
[Creación manual de contenedores](how-to-create-wrappers-manually.md)   
Describe cómo crear manualmente un contenedor COM en código fuente administrado. 
 
 [Cómo: Migrar código administrado DCOM a WCF](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 Describe cómo migrar código DCOM administrado a WCF para obtener la solución más segura.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Tipos de datos COM](https://msdn.microsoft.com/library/sak564ww(v=vs.100).aspx)  
 Proporciona los tipos de datos administrados y no administrados correspondientes.  
  
 [Personalización de contenedores CCW](https://msdn.microsoft.com/library/3bwc828w(v=vs.100).aspx)  
 Describe cómo serializar tipos de datos explícitamente mediante el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> en tiempo de diseño.  
  
 [Personalización de contenedores RCW](https://msdn.microsoft.com/library/e753eftz(v=vs.100).aspx)  
 Describe cómo ajustar el comportamiento de serialización de tipos en un ensamblado de interoperabilidad y cómo definir tipos COM manualmente.  
  
 [Interoperabilidad COM avanzada](https://msdn.microsoft.com/library/bd9cdfyx(v=vs.100).aspx)  
 Proporciona vínculos a más información sobre la incorporación de componentes COM en una aplicación de .NET Framework.  
  
 [Resumen de la conversión de ensamblados en bibliotecas de tipos](https://msdn.microsoft.com/library/xk1120c3(v=vs.100).aspx)  
 Describe el proceso de conversión de la exportación de ensamblado a biblioteca de tipos.  
  
 [Resumen de la conversión de bibliotecas de tipos en ensamblados](https://msdn.microsoft.com/library/k83zzh38(v=vs.100).aspx)  
 Describe el proceso de conversión de la importación de biblioteca de tipos a ensamblado.  
  
 [Interoperar mediante tipos genéricos](https://msdn.microsoft.com/library/ms229590(v=vs.100).aspx)  
 Describe qué acciones se admiten al usar tipos genéricos para la interoperabilidad COM.
