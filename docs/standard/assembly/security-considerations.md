---
title: Consideraciones de seguridad sobre ensamblados
description: Cuando se compila un ensamblado .NET, se pueden especificar los permisos que son necesarios para su ejecución. En este artículo se describen los ensamblados con nombre seguro y las herramientas de firma.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], security
- signcodes
- names [.NET Framework], assemblies
- strong-named assemblies, security considerations
- signing assemblies
- assemblies [.NET Framework], signing
- granting permissions, assemblies
- assemblies [.NET Framework], strong-named
- names [.NET Framework], strong names
- permissions [.NET Framework], assemblies
- security [.NET Framework], assemblies
- integrity with assemblies
ms.assetid: 1b5439c1-f3d5-4529-bd69-01814703d067
ms.openlocfilehash: d0b822f725444248d1037c21ffea9afe1cebb7e2
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290024"
---
# <a name="assembly-security-considerations"></a>Consideraciones de seguridad sobre ensamblados
Cuando se compila un ensamblado, se puede especificar el conjunto de permisos que son necesarios para la ejecución del mismo. La concesión de permisos específicos para un ensamblado se basa en la evidencia.  
  
 La evidencia se utiliza de dos formas distintas:  
  
- La evidencia de entrada se combina con la evidencia recopilada por el cargador para crear un juego final de evidencias que se utiliza en la resolución de directivas. Entre los métodos que utilizan esta semántica se incluyen: **Assembly.Load**, **Assembly.LoadFrom** y **Activator.CreateInstance**.  
  
- La evidencia de entrada se utiliza sin modificaciones como el conjunto final de evidencias utilizadas en la resolución de directivas. Entre los métodos que utilizan esta semántica se incluyen: **Assembly.Load(byte[])** y **AppDomain.DefineDynamicAssembly()** .  
  
  Se pueden conceder permisos opcionales mediante la [directiva de seguridad](../../framework/misc/code-access-security-basics.md) establecida en el equipo donde se ejecutará el ensamblado. Si desea que su código controle todas las posibles excepciones de seguridad, puede:  
  
- Insertar una solicitud de permiso para todos los permisos que deba tener su código y controlar por adelantado los errores que se puedan producir en tiempo de carga si no se conceden tales permisos.  
  
- No utilizar una solicitud de permiso para obtener los permisos que pueda necesitar su código, pero estar preparado para controlar las excepciones de seguridad que se pueden producir si no se conceden los permisos.  
  
  > [!NOTE]
  > La seguridad es una cuestión compleja, con muchas opciones posibles entre las que elegir. Para más información, consulte [Conceptos clave de seguridad](../security/key-security-concepts.md).  
  
 En el momento de la carga, se utiliza la evidencia del ensamblado como entrada para la directiva de seguridad. El administrador del equipo y la empresa y la configuración de directivas de usuario establecen la directiva de seguridad, que determina el conjunto de permisos que se concede a todo el código administrado cuando se ejecuta. La directiva de seguridad se puede establecer para la compañía del ensamblado (si tiene una firma generada utilizando la herramienta de firma), para el sitio y la zona Web (en términos de Internet Explorer) de los que se descargó el ensamblado o para el nombre seguro del ensamblado. Por ejemplo, el administrador de un equipo puede establecer una directiva de seguridad que permita que todo el código descargado desde un sitio Web y firmado por una compañía de software dada pueda tener acceso a una base de datos del equipo, pero no le otorga permiso para escribir en el disco del equipo.  
  
## <a name="strong-named-assemblies-and-signing-tools"></a>Ensamblados con nombre seguro y herramientas de firma  

 > [!WARNING]
 > Para garantizar la seguridad, no confíe únicamente en el uso de nombres seguros. Estos solo proporcionan una identidad única.

 Se puede firmar un ensamblado de dos formas diferentes y, a la vez, complementarias: con un nombre seguro o utilizando [SignTool.exe (Herramienta de firma)](../../framework/tools/signtool-exe.md). Al firmar un ensamblado con un nombre seguro, se agrega un cifrado mediante clave pública al archivo que contiene el manifiesto del ensamblado. La firma mediante nombres seguros ayuda a comprobar la unicidad del nombre, impide la simulación de nombres y proporciona a los llamadores alguna identidad cuando se resuelve una referencia.  
  
 No hay ningún nivel de confianza asociado a un nombre seguro, lo que hace que [SignTool.exe (Sign Tool)](../../framework/tools/signtool-exe.md) adquiera un carácter importante. Las dos herramientas de firma requieren que una compañía de software demuestre su identidad a una autoridad de terceros y obtenga un certificado. Este certificado se incrusta en el archivo y el administrador puede utilizarlo para decidir si debe confiar en la autenticidad del código.  
  
 Es posible asignar un nombre seguro y una firma digital creadas mediante la utilización de [SignTool.exe (Sign Tool)](../../framework/tools/signtool-exe.md) en un ensamblado, o se puede utilizar cualquiera de las dos opciones por separado. Ambas herramientas de firma sólo pueden firmar archivos de uno en uno; en el caso de un ensamblado de múltiples archivos, se firma el archivo que contiene el manifiesto del ensamblado. Se almacena un nombre seguro en el archivo que contiene el manifiesto del ensamblado, pero la firma creada mediante la utilización de [SignTool.exe (Sign Tool)](../../framework/tools/signtool-exe.md) se almacena en una ranura reservada del archivo ejecutable portable (PE) que contiene el manifiesto. Se puede utilizar la firma de un ensamblado (con o sin nombre seguro) mediante [SignTool.exe (Sign Tool)](../../framework/tools/signtool-exe.md) cuando ya se disponga de una jerarquía de confianza que se base en firmas generadas de [SignTool.exe (Sign Tool)](../../framework/tools/signtool-exe.md) o cuando una determinada directiva utilice solo la parte de la clave y no compruebe una cadena de confianza.  
  
> [!NOTE]
> Cuando se utilicen tanto un nombre seguro como una firma de la herramienta de firma en un ensamblado, primero se debe asignar el nombre seguro.  
  
 Common Language Runtime también realiza una comprobación de código hash; el manifiesto del ensamblado contiene una lista de todos los archivos que componen el ensamblado, incluido el código hash de cada archivo que existía cuando se compiló el manifiesto. A medida que se carga cada uno de los archivos, se aplica un algoritmo hash a su contenido y se compara con el valor hash almacenado en el manifiesto. Si los dos valores hash no coinciden, el ensamblado no se carga.  
  
 Debido a que los nombres seguros y las firmas que utilizan [SignTool.exe (Sign Tool)](../../framework/tools/signtool-exe.md) garantizan la integridad, se puede basar la directiva de seguridad de acceso del código en estas dos formas de evidencia de ensamblado. Los nombres seguros y las firmas que utilizan [SignTool.exe (Sign Tool)](../../framework/tools/signtool-exe.md) garantizan la integridad mediante firmas digitales y certificados. Todas las tecnologías mencionadas (comprobación de código hash, nombres seguros y firmas que utilizan [SignTool.exe (Sign Tool)](../../framework/tools/signtool-exe.md)) se combinan para garantizar que el ensamblado no ha sufrido ninguna alteración.  
  
## <a name="see-also"></a>Vea también

- [Ensamblados con nombre seguro](strong-named.md)
- [Ensamblados de .NET](index.md)
- [SignTool.exe (Herramienta de firma)](../../framework/tools/signtool-exe.md)
