---
title: Ejemplo UriTemplate
ms.date: 03/30/2017
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
ms.openlocfilehash: fb956882ae653f584026fefb20e261c90010ca9b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591064"
---
# <a name="uritemplate-sample"></a>Ejemplo UriTemplate
La clase <xref:System.UriTemplate> proporciona los métodos por trabajar con conjuntos de URI que comparten una estructura común. Este ejemplo muestra los siguientes conceptos clave relacionados con `UriTemplate`:  
  
- Sintaxis para crear plantillas.  
  
- Crear instancias de URI de una `UriTemplate` utilizando los métodos <xref:System.UriTemplate.BindByName%2A> y <xref:System.UriTemplate.BindByPosition%2A>.  
  
- El método <xref:System.UriTemplateTable.Match%2A>, que es la operación inversa de `BindByName` y `BindByPosition`.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
2. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## <a name="see-also"></a>Vea también

- [Tabla UriTemplate](uritemplate-table-sample.md)
- [Distribuidor de tabla UriTemplate](uritemplate-table-dispatcher-sample.md)
