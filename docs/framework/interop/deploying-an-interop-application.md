---
title: Implementar una aplicación interoperativa
description: Implemente una aplicación de interoperabilidad, que normalmente tiene un ensamblado de cliente de .NET, ensamblados de interoperabilidad de distintas bibliotecas de tipos COM y componentes COM registrados.
ms.date: 03/30/2017
helpviewer_keywords:
- deploying applications [.NET Framework], interop
- strong-named assemblies, interop applications
- unsigned assemblies
- private assemblies
- exposing COM components to .NET Framework
- interoperation with unmanaged code, deploying applications
- shared assemblies
- COM interop, deploying applications
- interoperation with unmanaged code, exposing COM components
- signed assemblies
- COM interop, exposing COM components
ms.assetid: ea8a403e-ae03-4faa-9d9b-02179ec72992
ms.openlocfilehash: 190b10ede4bc0037836d44332408d7752108346c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555073"
---
# <a name="deploying-an-interop-application"></a>Implementar una aplicación interoperativa
Una aplicación de interoperabilidad suele incluir un ensamblado de cliente de .NET, uno o varios ensamblados de interoperabilidad que representan diferentes bibliotecas de tipos COM, y uno o varios componentes COM registrados. Visual Studio y Windows SDK proporcionan herramientas para importar y convertir una biblioteca de tipos en un ensamblado de interoperabilidad, tal como se describe en [Importar una biblioteca de tipos como un ensamblado](importing-a-type-library-as-an-assembly.md). Hay dos maneras de implementar una aplicación de interoperabilidad:  
  
- Mediante tipos de interoperabilidad insertados: A partir de .NET Framework 4, se puede indicar al compilador que inserte información de tipos de un ensamblado de interoperabilidad en el archivo ejecutable. El compilador solo inserta la información de tipos que la aplicación usa. No es necesario implementar el ensamblado de interoperabilidad con la aplicación. Esta es la técnica recomendada.  
  
- Mediante la implementación de ensamblados de interoperabilidad: se puede crear una referencia estándar a un ensamblado de interoperabilidad. En este caso, el ensamblado de interoperabilidad debe implementarse con la aplicación. Si emplea esta técnica y no usa ningún componente COM privado, haga siempre referencia al ensamblado de interoperabilidad primario (PIA) publicado por el autor del componente COM que va a incorporar en el código administrado. Para más información sobre cómo generar y usar ensamblados de interoperabilidad primarios, vea [Ensamblados de interoperabilidad primarios](/previous-versions/dotnet/netframework-4.0/aax7sdch(v=vs.100)).  
  
 Si usa tipos de interoperabilidad insertados, la implementación es sencilla y directa. No es necesario hacer nada especial. En el resto de este artículo se describen los escenarios para implementar ensamblados de interoperabilidad con la aplicación.  
  
## <a name="deploying-interop-assemblies"></a>Implementar ensamblados de interoperabilidad  
 Los ensamblados pueden tener nombres seguros. Un ensamblado con nombre seguro incluye la clave pública del editor, que proporciona una identidad única. Los ensamblados generados por el [importador de la biblioteca de tipos (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) pueden estar firmados por el publicador mediante la opción **/keyfile**. Puede instalar ensamblados firmados en la caché global de ensamblados. Los ensamblados no firmados deben instalarse en el equipo del usuario como ensamblados privados.  
  
### <a name="private-assemblies"></a>Ensamblados privados  
 Para instalar un ensamblado que se va a usar de forma privada, el archivo ejecutable de la aplicación y el ensamblado de interoperabilidad que contiene los tipos COM importados deben instalarse en la misma estructura de directorios. En la ilustración siguiente se muestra un ensamblado de interoperabilidad sin firma que se va a usar de forma privada por parte de Client1.exe y Client2.exe, que residen en directorios de aplicación diferentes. El ensamblado de interoperabilidad, denominado LOANLib.dll en este ejemplo, se instala dos veces.  
  
 ![Estructura de directorios y Registro de Windows](./media/deploying-an-interop-application/com-private-deployment.gif "Estructura de directorios y entradas del Registro para una implementación privada")  
  
 Todos los componentes COM asociados a la aplicación deben instalarse en el Registro de Windows. Si Client1.exe y Client2.exe en la ilustración se instalan en equipos diferentes, debe registrar los componentes COM en ambos equipos.  
  
### <a name="shared-assemblies"></a>Ensamblados compartidos  
 Los ensamblados que se comparten entre varias aplicaciones deben instalarse en un repositorio centralizado, denominado caché global de ensamblados. Los clientes de .NET pueden tener acceso a la misma copia del ensamblado de interoperabilidad, que se firma y se instala en la caché global de ensamblados. Para más información sobre cómo generar y usar ensamblados de interoperabilidad primarios, vea [Ensamblados de interoperabilidad primarios](/previous-versions/dotnet/netframework-4.0/aax7sdch(v=vs.100)).  
  
## <a name="see-also"></a>Vea también

- [Exponer componentes COM en .NET Framework](exposing-com-components.md)
- [Importar una biblioteca de tipos como un ensamblado](importing-a-type-library-as-an-assembly.md)
- [Uso de tipos COM en código administrado](/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))
- [Compilar un proyecto de interoperabilidad](compiling-an-interop-project.md)
