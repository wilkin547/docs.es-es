---
title: "My.WebServices (Objeto) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "My.WebServices"
  - "My.MyProject.WebServices"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.WebServices (objeto)"
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# My.WebServices (Objeto)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Proporciona propiedades para crear y tener acceso a una instancia única de cada servicio Web XML al que hace referencia el proyecto actual.  
  
## Comentarios  
 El objeto `My.WebServices` proporciona una instancia de cada servicio Web al que hace referencia el proyecto actual.  Cada una de las instancias se crea a petición.  Puede tener acceso a estos servicios Web a través de las propiedades del objeto `My.WebServices`.  El nombre de la propiedad es igual que el nombre del servicio Web al que tiene acceso la propiedad.  Cualquier clase que herede de <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> es un servicio Web.  Para obtener información sobre cómo agregar servicios Web a un proyecto, vea [Acceso a los servicios Web de la aplicación](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 El objeto `My.WebServices` expone sólo los servicios Web asociados al proyecto actual.  No proporciona acceso a servicios Web declarados en archivos DLL a los que se hace referencia.  Para tener acceso a un servicio Web que un archivo DLL proporciona, debe utilizar el nombre completo del servicio Web, con el formato *nombreDeDll*.*nombreDeServicioWeb*.  Para obtener más información, vea [Acceso a los servicios Web de la aplicación](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 El objeto y sus propiedades no están disponibles para las aplicaciones Web.  
  
## Propiedades  
 Cada propiedad del objeto `My.WebServices` proporciona acceso a una instancia de un servicio Web al que hace referencia el proyecto actual.  El nombre de la propiedad es el mismo que el del servicio Web al que la propiedad tiene acceso y el tipo de propiedad es igual que el tipo de servicio Web.  
  
> [!NOTE]
>  Si hay un conflicto de nombres, el nombre de la propiedad para tener acceso a un servicio Web es *espacioDeNombresRaíz*\_*espacioDeNombres*\_*nombreDeServicio*.  Por ejemplo, considere dos servicios Web denominados `Service1`.  Si uno de estos servicios está en el espacio de nombres raíz `WindowsApplication1` y en el espacio de nombres `Namespace1`, obtendría acceso a ese servicio mediante `My.WebServices.WindowsApplication1_Namespace1_Service1`.  
  
 Cuando se tiene acceso por primera vez a una de las propiedades del objeto `My.WebServices`, éste crea una nueva instancia del servicio Web y la almacena.  Los accesos siguientes a la propiedad devuelven esa instancia del servicio Web.  
  
 Puede desechar un servicio Web asignando `Nothing` a la propiedad de ese servicio Web.  El establecedor de la propiedad asigna `Nothing` al valor almacenado.  Si se asigna un valor distinto de `Nothing` a la propiedad, el establecedor produce una excepción <xref:System.ArgumentException>.  
  
 Puede probar si una propiedad del objeto `My.WebServices` almacena una instancia del servicio Web mediante el operador `Is` o `IsNot`.  Puede utilizar esos operadores para comprobar si el valor de la propiedad es `Nothing`.  
  
> [!NOTE]
>  Normalmente, el operador `Is` o `IsNot` tiene que leer el valor de la propiedad para realizar la comparación.  Sin embargo, si la propiedad almacena actualmente `Nothing`, crea una nueva instancia del servicio Web y, a continuación, devuelve esa instancia.  No obstante, el compilador de Visual Basic trata las propiedades del objeto `My.WebServices` de forma especial y permite al operador `Is` o `IsNot` comprobar el estado de la propiedad sin cambiar su valor.  
  
## Ejemplo  
 Este ejemplo llama al método `FahrenheitToCelsius` del servicio Web XML `TemperatureConverter` y devuelve el resultado.  
  
 [!code-vb[VbVbalrMyWebService#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-webservices-object_1.vb)]  
  
 Para que este ejemplo funcione, el proyecto debe hacer referencia a un servicio Web denominado `Converter` y ese servicio Web debe exponer el método `ConvertTemperature`.  Para obtener más información, vea [Acceso a los servicios Web de la aplicación](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Este código no funciona en un proyecto de aplicación Web.  
  
## Requisitos  
  
### Disponibilidad por tipo de proyecto  
  
|||  
|-|-|  
|Tipo de proyecto|Disponible|  
|Aplicación Windows|**Sí**|  
|Biblioteca de clases|**Sí**|  
|Aplicación de consola|**Sí**|  
|Biblioteca de controles de Windows|**Sí**|  
|Biblioteca de controles Web|**Sí**|  
|Servicio de Windows|**Sí**|  
|Sitio Web|No|  
  
## Vea también  
 <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>   
 <xref:System.ArgumentException>   
 [Acceso a los servicios Web de la aplicación](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)