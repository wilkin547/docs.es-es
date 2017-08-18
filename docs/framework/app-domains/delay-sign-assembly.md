---
title: Retrasar la firma de un ensamblado
ms.date: 07/31/2017
ms.prod: .net-framework
ms.technology:
- dotnet-bcl
ms.topic: article
helpviewer_keywords:
- deferring assembly signing
- signing assemblies
- assemblies [.NET Framework], signing
- strong-named assemblies, delaying assembly signing
- partial assembly signing
ms.assetid: 9d300e17-5bf1-4360-97da-2aa55efd9070
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 0ee5fed355e0d8418500f1ecee53019548d9f7f8
ms.openlocfilehash: 2c50a652c834dba80595f2ea419bc75148e13419
ms.contentlocale: es-es
ms.lasthandoff: 08/02/2017

---
# <a name="delay-signing-an-assembly"></a>Retrasar la firma de un ensamblado
Una organización podría tener un par de claves muy bien guardado al que los desarrolladores no tuvieran acceso cada día. La clave pública suele estar disponible, pero el acceso a la clave privada estaría restringido a algunas personas. Al desarrollar ensamblados con nombres seguros, cada ensamblado que hace referencia al ensamblado de destino con nombre seguro contiene el token de la clave pública usada para asignar un nombre seguro al ensamblado de destino. Esto requiere que la clave pública esté disponible durante el proceso de desarrollo.  
  
 Puede usar la firma retardada o parcial en tiempo de compilación para reservar espacio en el archivo portable ejecutable (PE) para la firma de nombre seguro, pero retrase la firma real hasta una fase posterior (normalmente justo antes de enviar el ensamblado).  
  
 En los pasos siguientes se describe el proceso para retrasar la firma de un ensamblado:  
  
1.  Se obtiene la parte de la clave pública del par de claves de la organización que se encargará de la firma. Normalmente, esta clave tiene la forma de un archivo .snk, que se puede crear mediante la [herramienta de nombre seguro (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) proporcionada por el [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].  
  
2.  Se anota el código fuente del ensamblado con dos atributos personalizados de <xref:System.Reflection>:  
  
    -   <xref:System.Reflection.AssemblyKeyFileAttribute>, que pasa el nombre del archivo que contiene la clave pública como parámetro a su constructor.  
  
    -   <xref:System.Reflection.AssemblyDelaySignAttribute>, que indica que se está retrasando la firma. Para ello, se pasa **true** como parámetro a su constructor. Por ejemplo:  
  
         [!code-cpp[AssemblyDelaySignAttribute#4](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cpp/source2.cpp#4)] [!code-csharp[AssemblyDelaySignAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cs/source2.cs#4)] [!code-vb[AssemblyDelaySignAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyDelaySignAttribute/vb/source2.vb#4)]  
  
3.  El compilador inserta la clave pública en el manifiesto del ensamblado y reserva espacio en el archivo PE para la firma de nombre seguro completo. La clave pública real se debe guardar mientras se compila el ensamblado para que otros ensamblados que hagan referencia a este puedan obtenerla y guardarla en su propia referencia al ensamblado.  
  
4.  Dado que el ensamblado no tiene una firma de nombre seguro válida, la comprobación de firma debe estar desactivada. Puede hacerlo mediante la opción **–Vr** con la herramienta de nombre seguro.  
  
     En el ejemplo siguiente se desactiva la comprobación para un ensamblado denominado `myAssembly.dll`.  
  
    ```  
    sn –Vr myAssembly.dll  
    ```  
  
     Para desactivar la comprobación en plataformas en las que no se puede ejecutar la herramienta de nombre seguro, como los microprocesadores de Advanced RISC Machine (ARM), use la opción **–Vk** para crear un archivo del Registro. Importe el archivo del Registro en el Registro del equipo en el que quiere desactivar la comprobación. En el ejemplo siguiente se crea un archivo del Registro para `myAssembly.dll`.  
  
    ```  
    sn –Vk myRegFile.reg myAssembly.dll  
    ```  
  
     Con la opción **–Vr** o **–Vk**, puede incluir opcionalmente un archivo .snk para probar la firma de la clave.  
  
    > [!WARNING]
    > Para garantizar la seguridad, no confíe únicamente en el uso de nombres seguros. Estos solo proporcionan una identidad única.
  
    > [!NOTE]
    >  Si usa la firma retardada durante el desarrollo con Visual Studio en un equipo de 64 bits y compila un ensamblado para **Cualquier CPU**, es posible que deba aplicar la opción **-Vr** dos veces. (En Visual Studio, **Cualquier CPU** es un valor de la propiedad de compilación **Destino de la plataforma**. Cuando se compila desde la línea de comandos, es el valor predeterminado). Para ejecutar la aplicación desde la línea de comandos o desde el Explorador de archivos, use la versión de 64 bits de [Sn.exe (herramienta de nombre seguro)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) para aplicar la opción **-Vr** al ensamblado. Para cargar el ensamblado en Visual Studio en tiempo de diseño (por ejemplo, si el ensamblado contiene componentes que usan otros ensamblados de la aplicación), use la versión de 32 bits de la herramienta de nombre seguro. Esto se debe a que el compilador Just-In-Time (JIT) compila el ensamblado en código nativo de 64 bits cuando el ensamblado se ejecuta desde la línea de comandos y en código nativo de 32 bits cuando el ensamblado se carga en el entorno de tiempo de diseño.  
  
5.  Después, normalmente justo antes del envío, se envía el ensamblado a la autoridad de firma de la organización para que lleve a cabo la firma de nombre seguro real mediante la opción **–R** con la herramienta de nombre seguro.  
  
     En el ejemplo siguiente se firma un ensamblado denominado `myAssembly.dll` con un nombre seguro mediante el par de claves `sgKey.snk`.  
  
    ```  
    sn -R myAssembly.dll sgKey.snk  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Crear ensamblados](../../../docs/framework/app-domains/create-assemblies.md)   
 [Cómo: Crear un par de claves privada y pública](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)   
 [Sn.exe (Herramienta de nombre seguro)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)   
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)

