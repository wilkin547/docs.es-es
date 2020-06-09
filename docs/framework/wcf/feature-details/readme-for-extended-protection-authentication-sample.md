---
title: Archivo ReadMe del ejemplo de protección extendida para la autenticación
ms.date: 03/30/2017
ms.assetid: 80bf2e97-398d-4db5-9040-d96478a2ccab
ms.openlocfilehash: 9b0a3535282a1fcc1103651f5601459e80d3d8d4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601106"
---
# <a name="readme-for-extended-protection-authentication-sample"></a>Archivo ReadMe del ejemplo de protección extendida para la autenticación

La protección ampliada es una iniciativa de seguridad para protegerse contra ataques de tipo "Man in the Middle" (MITM), en los que un atacante ("Man in the Middle") intercepta las credenciales de un cliente y las utiliza para obtener acceso a recursos seguros en el servidor previsto del cliente.

Para obtener más información, vea [información general sobre protección ampliada para la autenticación](extended-protection-for-authentication-overview.md).

> [!NOTE]
> Esta muestra solo funciona cuando se hospeda en IIS. No funciona en el servidor de desarrollo de Visual Studio, ya que este no admite HTTPS.

## <a name="to-set-up-build-and-run-the-sample"></a>Para configurar, compilar y ejecutar el ejemplo

1. Instale IIS en el equipo desde agregar o quitar programas-> características de Windows.

2. Active la autenticación de Windows en características de Windows: Internet Information Services > World Wide Web Services-> Security-> autenticación de Windows.

3. Active la activación HTTP en las características de Windows: Microsoft .NET Framework 3.5.1-> Windows Communication Foundation la activación HTTP.

4. Este ejemplo requiere que el cliente establezca un canal seguro con el servidor, por lo que es necesaria la presencia de un certificado de servidor que se puede instalar desde el Administrador de Internet Information Services (IIS).

    1. Abra el administrador de IIS: certificados de servidor de > (en la pestaña vista de características).

    2. Con fines de prueba de esta muestra, puede crear un certificado autofirmado. (Si no desea que Internet Explorer le indique que el certificado no es seguro, puede instalarlo en el almacén Entidades emisoras de certificados raíz de confianza).

5. Vaya al panel Acciones del sitio web predeterminado. Haga clic en Editar > enlaces del sitio. Agregue HTTPS como tipo si aún no está presente, con el número de puerto 443, y asigne el certificado SSL creado en el paso anterior.

6. Compile el servicio. Esto crea un directorio virtual en IIS (a partir de la acción posterior a la compilación especificada en las propiedades del proyecto) y copia los archivos dll, .svc y config según sea necesario para que un servicio se hospede en web.

7. Abra el Administrador de IIS. Haga clic con el botón secundario en el directorio virtual (ExtendedProtection) que creó en el paso anterior y seleccione Convertir en aplicación.

8. Abra el módulo de autenticación en el Administrador de IIS para este directorio virtual y habilite la autenticación de Windows.

9. Abra la Configuración avanzada de la autenticación de Windows para este directorio virtual y establézcala en Requerida, ya que en el ejemplo el valor ExtendedProtection correspondiente está establecido en Siempre.

10. Puede probar el servicio obteniendo acceso a la dirección URL desde una ventana del explorador. Si desea tener acceso a esta dirección URL desde varios equipos, asegúrese de que el firewall está abierto para todas las conexiones HTTP y HTTPS entrantes.

11. Abra el archivo de configuración del cliente y proporcione un nombre de equipo completo para el \<client>  -  \<endpoint> atributo-address y reemplace \<full_machine_name> .

12. Ejecute el cliente. El cliente se comunica con el servicio estableciendo un canal seguro y usando la protección extendida.
