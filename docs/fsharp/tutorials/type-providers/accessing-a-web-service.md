---
title: 'Tutorial: obtener acceso a un servicio Web mediante proveedores de tipo (F #)'
description: "Obtenga información acerca de cómo usar el proveedor de tipo de lenguaje de descripción de servicios Web (WSDL) disponible en F # 3.0 para tener acceso a un servicio de WSDL."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 63374fa9-8fb8-43ac-bcb9-ef2290d9f851
ms.openlocfilehash: 06d955033d465cf58af05f483d21175f90d1777a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-accessing-a-web-service-by-using-type-providers"></a>Tutorial: Obtener acceso a un servicio Web mediante proveedores de tipos

> [!NOTE]
Esta guía se escribió para F # 3.0 y se actualizará.  Vea [FSharp.Data](http://fsharp.github.io/FSharp.Data/) para obtener información sobre los proveedores de tipos multiplataforma actualizados.

> [!NOTE]
Los vínculos de referencia de API le llevará a MSDN.  La referencia de API de docs.microsoft.com no está completa.

En este tutorial se muestra cómo usar el proveedor de tipo de lenguaje de descripción de servicios Web (WSDL) que está disponible en F # 3.0 para tener acceso a un servicio de WSDL. En otros lenguajes. NET, generar el código para acceder al servicio web que realiza la llamada svcutil.exe o al agregar una referencia web en, por ejemplo, un proyecto de C# para obtener Visual Studio para llamar a svcutil.exe para usted. En F #, tiene la opción adicional de usar el proveedor de tipos WSDL, por lo que tan pronto como se escribe el código que crea el tipo WsdlService, los tipos se generan y estén disponibles. Este proceso se basa en el servicio que está disponible cuando se escribe el código.

En este tutorial se muestran las tareas siguientes. Debe completarlos en el orden para el tutorial sea correcta:


- Crear el proyecto
<br />

- Configurar el proveedor de tipos
<br />

- Llamar al servicio web y procesar los resultados
<br />


## <a name="creating-the-project"></a>Crear el proyecto
En el paso, cree un proyecto y agregar las referencias adecuadas para usar un proveedor de tipo WSDL.


#### <a name="to-create-and-set-up-an-f-project"></a>Para crear y configurar un proyecto de F#

1. Abra un nuevo proyecto de aplicación de consola de F #.
<br />

2. En **el Explorador de soluciones**, abra el menú contextual para el proyecto **referencia** nodo y, a continuación, elija **Agregar referencia**.
<br />

3. En el **ensamblados** área, elija **Framework**y, a continuación, en la lista de ensamblados disponibles, elija **System.Runtime.Serialization** y  **System.ServiceModel**.
<br />

4. En el **ensamblados** área, elija **extensiones**.
<br />

5. En la lista de ensamblados disponibles, elija **FSharp.Data.TypeProviders**y, a continuación, elija la **Aceptar** botón para agregar referencias a estos ensamblados.
<br />

## <a name="configuring-the-type-provider"></a>Configurar el proveedor de tipos
En este paso, usa el proveedor de tipos WSDL para generar tipos para el servicio web TerraServer.


#### <a name="to-configure-the-type-provider-and-generate-types"></a>Para configurar el proveedor de tipo y generar tipos

1. Agregue la siguiente línea de código para abrir el espacio de nombres del proveedor de tipo.
<br />

```fsharp
open System
open System.ServiceModel
open Microsoft.FSharp.Linq
open Microsoft.FSharp.Data.TypeProviders
```

2. Agregue la siguiente línea de código para invocar el proveedor de tipos con un servicio web. En este ejemplo, utilice el servicio web TerraServer.
<br />

```fsharp
type TerraService = WsdlService<" HYPERLINK "http://terraserver-usa.com/TerraService2.asmx?WSDL" http://msrmaps.com/TerraService2.asmx?WSDL">
```

  Si el URI del servicio está mal escrito o si el propio servicio está inactivo o no está funcionando, aparece un subrayado ondulado de color rojo debajo de esta línea de código. Si eliges el código, un mensaje de error describe el problema. Puede obtener la misma información en el **lista de errores** ventana o en la **ventana de salida** después de la compilación.
<br />  Hay dos maneras de especificar valores de configuración para una conexión de WSDL, mediante el archivo app.config para el proyecto, o mediante los parámetros de tipo estático en la declaración del proveedor de tipo. Puede utilizar svcutil.exe para generar elementos del archivo de configuración adecuado. Para obtener más información acerca de cómo utilizar svcutil.exe para generar información de configuración para un servicio web, consulte [ServiceModel Metadata Utility Tool &#40; Svcutil.exe &#41; ](https://msdn.microsoft.com/library/aa347733.aspx). Para obtener una descripción completa de los parámetros de tipo estático para el proveedor de tipos WSDL, vea [proveedor de tipos WsdlService](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d).
<br />

## <a name="calling-the-web-service-and-processing-the-results"></a>Llamar al servicio web y procesar los resultados
Cada servicio web tiene su propio conjunto de tipos que se utilizan como parámetros para sus llamadas de método. En este paso, preparar estos parámetros, llamar a un método web y procesar la información que devuelve.


#### <a name="to-call-the-web-service-and-process-the-results"></a>Para llamar al servicio web y procesar los resultados

1. El servicio web podría agotar tiempo de espera o deje de funcionar, por lo que debe incluir la llamada del servicio web en un bloque de control de excepciones. Escribir el código siguiente para intentar obtener datos desde el servicio web.
<br />

```fsharp
try
  let terraClient = TerraService.GetTerraServiceSoap ()
  let myPlace = new TerraService.ServiceTypes.msrmaps.com.Place(City = "Redmond", State = "Washington", Country = "United States")
  let myLocation = terraClient.ConvertPlaceToLonLatPt(myPlace)
  printfn "Redmond Latitude: %f Longitude: %f" (myLocation.Lat) (myLocation.Lon)
with
| :? ServerTooBusyException as exn ->
  let innerMessage =
    match (exn.InnerException) with
    | null -> ""
    | innerExn -> innerExn.Message
  printfn "An exception occurred:\n %s\n %s" exn.Message innerMessage
| exn -> printfn "An exception occurred: %s" exn.Message
```

Tenga en cuenta que crear los tipos de datos que son necesarios para el servicio web, como **lugar** y **ubicación**, como un tipo de los tipos anidados en el WsdlService **TerraService**.
<br />


## <a name="see-also"></a>Vea también
[Proveedor de tipos WsdlService](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d)

[Proveedores de tipos](index.md)
