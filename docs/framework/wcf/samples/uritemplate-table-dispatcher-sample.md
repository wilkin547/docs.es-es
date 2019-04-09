---
title: Ejemplo de distribuidor de tabla de UriTemplate
ms.date: 03/30/2017
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
ms.openlocfilehash: ff697a205ce47960275b51153d415af717f81222
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156018"
---
# <a name="uritemplate-table-dispatcher-sample"></a>Ejemplo de distribuidor de tabla de UriTemplate
La clase <xref:System.UriTemplateTable> proporciona una estructura de tabla asociativa similar a un diccionario para trabajar con un conjunto de instancias de <xref:System.UriTemplate>. Este ejemplo muestra un motor de distribución básico generado usando `UriTemplateTable`, un escenario de uso común para la clase `UriTemplateTable`.  
  
 Este ejemplo muestra los conceptos clave siguientes para la clase `UriTemplateTable`:  
  
-   Asociar los delegados a `UriTemplates` en `UriTemplateTable`.  
  
-   Utilizar <xref:System.UriTemplateTable.MatchSingle%2A> para obtener el delegado del controlador correcto para un URI determinado.  
  
-   Invocar el delegado de controlador para procesar la solicitud.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## <a name="see-also"></a>Vea también

- [Tabla UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)
- [UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
