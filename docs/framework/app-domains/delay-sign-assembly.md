---
title: "Retrasar la firma de un ensamblado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "aplazar la firma de un ensamblado"
  - "firmar ensamblados"
  - "ensamblados [.NET Framework], firmar"
  - "ensamblados con nombre seguro, retrasar la firma de un ensamblado"
  - "firma parcial de un ensamblado"
ms.assetid: 9d300e17-5bf1-4360-97da-2aa55efd9070
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Retrasar la firma de un ensamblado
Una organización puede tener un par de claves muy bien guardado al que los programadores no tiene acceso todos los días.  La clave pública está disponible con frecuencia, pero la clave privada está restringida sólo a algunas personas.  Al programar ensamblados con nombre seguro, cada ensamblado que hace referencia al ensamblado con nombre seguro de destino contiene el token de la clave pública que se usa para dar al ensamblado de destino un nombre seguro.  Ello requiere que la clave pública esté disponible durante el proceso de programación.  
  
 Se puede usar el retraso de firma o firma parcial en tiempo de compilación para reservar espacio en el archivo ejecutable portable \(PE\) para la firma de nombre seguro, pero la firma en sí se retrasa hasta más adelante, normalmente justo antes del envío del ensamblado.  
  
 Los pasos siguientes describen el proceso de retraso de la firma de un ensamblado:  
  
1.  Obtenga la parte de clave pública del par de claves de la organización que, en su momento, llevará a cabo la firma.  Normalmente, esta clave es un archivo .snk, que se puede crear con la [herramienta Nombre seguro \(Sn.exe\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) que proporciona [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].  
  
2.  Agregue al código fuente del ensamblado dos atributos personalizados de <xref:System.Reflection>:  
  
    -   <xref:System.Reflection.AssemblyKeyFileAttribute>, que pasa el nombre del archivo que contiene la clave pública como parámetro a su constructor.  
  
    -   <xref:System.Reflection.AssemblyDelaySignAttribute>, que indica que se va a utilizar el retraso de firma pasando **true** como parámetro a su constructor.  Por ejemplo:  
  
         [!code-cpp[AssemblyDelaySignAttribute#4](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cpp/source2.cpp#4)]
         [!code-csharp[AssemblyDelaySignAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cs/source2.cs#4)]
         [!code-vb[AssemblyDelaySignAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyDelaySignAttribute/vb/source2.vb#4)]  
  
3.  El compilador inserta la clave pública en el manifiesto del ensamblado y reserva espacio en el archivo PE para la firma de nombre seguro completa.  La clave pública auténtica se debe guardar mientras se compila el ensamblado para que otros ensamblados que hagan referencia a éste puedan obtenerla y guardarla en su propia referencia al ensamblado.  
  
4.  Como el ensamblado no tiene una firma de nombre seguro válida, hay que desactivar la comprobación de esa firma.  Esto se hace utilizando la opción **–Vr** con la herramienta Nombre seguro.  
  
     En el ejemplo siguiente se desactiva la comprobación para un ensamblado denominado `myAssembly.dll`.  
  
    ```  
    sn –Vr myAssembly.dll  
    ```  
  
     Para desactivar la comprobación en plataformas donde no se puede ejecutar la Herramienta de nombre seguro, como microprocesadores de \(ARM\) de equipo de la Computación avanzada RISC, utilice la opción de **–Vk** de crear un archivo de registro.  Importe el archivo de registro del registro en el equipo donde desea desactivar la comprobación.  El ejemplo siguiente se crea un archivo de registro para `myAssembly.dll`.  
  
    ```  
    sn –Vk myRegFile.reg myAssembly.dll  
    ```  
  
     Con **–Vr** o la opción de **–Vk** , puede incluir de forma opcional un archivo .snk para firmar de prueba.  
  
    > [!CAUTION]
    >  Utilice la opción de **\-Vr** o de **–Vk** solo durante el desarrollo.  Al agregar un ensamblado a la lista de omisiones de comprobación se produce una vulnerabilidad en la seguridad.  Puede que un ensamblado malicioso utilice el nombre completo especificado \(nombre de ensamblado, versión, referencia cultural y token de clave pública\) del ensamblado existente en la lista de omisiones de comprobación para imitar su identidad.  Esto permitiría que el ensamblado malintencionado se pasase también por alto durante la comprobación.  
  
    > [!NOTE]
    >  Si utiliza la firma retardada durante desarrollo con Visual Studio en un equipo 64 bits, y compila un ensamblado para **Cualquier CPU**, podría tener que aplicar la opción **\-Vr** dos veces. \(En Visual Studio, **Cualquier CPU** es un valor de la propiedad de compilación **Destino de la plataforma**; al compilar desde la línea de comandos, es el valor predeterminado.\) Para ejecutar la aplicación desde la línea de comandos o desde el archivo del Explorador, utilice la versión de 64 bits de [Sn.exe \(Strong Name Tool\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) para aplicar la opción de **\-Vr** al ensamblado.  Para cargar el ensamblado en Visual Studio en tiempo de diseño \(por ejemplo, si el ensamblado contiene componentes que utilizan otros ensamblados de la aplicación\), utilice la versión de 32 bits de la herramienta de nombre seguro.  Esto se debe a que el compilador Just\-In\-Time \(JIT\) compila el ensamblado a código nativo de 64 bits cuando el ensamblado se ejecuta desde la línea de comandos, y a código nativo de 32 bits cuando se carga en el entorno en tiempo de diseño.  
  
5.  Posteriormente, por lo general justo antes del envío, el ensamblado se entrega a la autoridad de firma de la organización para que lleve a cabo la firma de nombre seguro propiamente dicha, utilizando la opción **–R** con la herramienta Nombre seguro.  
  
     En el ejemplo siguiente se firma el ensamblado `myAssembly.dll` con un nombre seguro utilizando el par de claves `sgKey.snk`.  
  
    ```  
    sn -R myAssembly.dll sgKey.snk  
    ```  
  
## Vea también  
 [Crear ensamblados](../../../docs/framework/app-domains/create-assemblies.md)   
 [Cómo: Crear un par de claves privada y pública](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)   
 [Sn.exe \(Strong Name Tool\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)   
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)