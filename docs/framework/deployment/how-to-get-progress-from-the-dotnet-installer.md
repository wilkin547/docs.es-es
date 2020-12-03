---
title: Procedimiento para obtener el progreso del instalador de .NET Framework 4.5
description: Obtenga información sobre cómo obtener el progreso del instalador de .NET Framework 4.5. Si desarrolla aplicaciones para esta versión de .NET, puede incluir (encadenar) el programa de instalación de .NET Framework 4.5 en el programa de instalación de la aplicación.
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- progress information, .NET Framework installer
- .NET Framework, installing
ms.assetid: 0a1a3ba3-7e46-4df2-afd3-f3a8237e1c4f
ms.openlocfilehash: 7e21a376c5a7551ecadeaa70c0a70968dc5752fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729127"
---
# <a name="how-to-get-progress-from-the-net-framework-45-installer"></a>Procedimiento para obtener el progreso del instalador de .NET Framework 4.5

.NET Framework 4.5 es un entorno de ejecución redistribuible. Si desarrolla aplicaciones para esta versión de .NET Framework, puede incluir (encadenar) el programa de instalación de .NET Framework 4.5 como un requisito previo para la instalación de su aplicación. Para presentar al usuario una experiencia de instalación personalizada o unificada, tal vez quiera iniciar silenciosamente el proceso de instalación de .NET Framework 4.5 y realizar su seguimiento mientras se muestra el progreso de la instalación de la aplicación. Con el fin de habilitar el seguimiento silencioso, el programa de instalación de .NET Framework 4.5 (que se puede observar) define un protocolo mediante el uso de un segmento de E/S asignado a la memoria (MMIO) para comunicarse con el programa de instalación (el proceso observador o encadenador). Este protocolo proporciona al encadenador una manera de obtener información de progreso, conseguir resultados detallados, responder a mensajes y cancelar el programa de instalación de .NET Framework 4.5.

- **Invocación**. Para llamar al programa de instalación de .NET Framework 4.5 y recibir información sobre el progreso de la sección MMIO, el programa de instalación debe hacer lo siguiente:

    1. Llamar al programa redistribuible de .NET Framework 4.5:

        `dotNetFx45_Full_x86_x64.exe /q /norestart /pipe section-name`

        donde *section name* es cualquier nombre que quiera usar para identificar a la aplicación. El programa de instalación de .NET Framework realiza operaciones asincrónicas de lectura y escritura en la sección MMIO, de modo que tal vez encuentre conveniente usar eventos y mensajes durante ese periodo. En el ejemplo, el proceso del programa de instalación de .NET Framework lo crea un constructor que asigna la sección MMIO (`TheSectionName`) y define un evento (`TheEventName`):

        ```cpp
        Server():ChainerSample::MmioChainer(L"TheSectionName", L"TheEventName")
        ```

        Sustituya esos nombres por nombres que sean únicos en su programa de instalación.

    2. Leer la sección MMIO. En .NET Framework 4.5, las operaciones de descarga e instalación son simultáneas: es posible que una parte de .NET Framework se esté instalando mientras la otra se descarga. Por tanto, el progreso se devuelve (es decir, se escribe) en la sección MMIO como dos números (`m_downloadSoFar` y `m_installSoFar`) que van subiendo desde 0 hasta 255. Cuando se escribe 255 y .NET Framework se cierra, la instalación se completa.

- **Códigos de salida**. Los códigos de salida siguientes que proceden del comando que llama al programa redistribuible de .NET Framework 4.5 indican si la instalación se ha realizado correctamente o no:

  - 0: la instalación se completó correctamente.

  - 3010: el programa de instalación se completó correctamente; es necesario reiniciar el sistema.

  - 1602: se ha cancelado la instalación.

  - Todos los demás códigos: se han producido errores en la instalación. Consulte los archivos de registro creados en %temp% para ver los detalles.

- **Cancelación de la instalación**. Puede cancelar la instalación en cualquier momento utilizando el método `Abort` para establecer las marcas `m_downloadAbort` y `m_ installAbort` en la sección MMIO.

## <a name="chainer-sample"></a>Ejemplo de encadenador

El ejemplo de Chainer inicia de forma silenciosa el programa de instalación de .NET Framework 4.5 y realiza un seguimiento de este mientras se muestra el progreso. Este ejemplo es similar al ejemplo de encadenador proporcionado para .NET Framework 4. Sin embargo, también puede evitar reinicios del sistema procesando el cuadro de mensaje para cerrar las aplicaciones de .NET Framework 4. Para más información sobre este cuadro de mensaje, vea el tema [Reducir los reinicios del sistema durante las instalaciones de .NET Framework 4.5](reducing-system-restarts.md). Puede usar este ejemplo con el programa de instalación de .NET Framework 4; en ese caso, el mensaje simplemente no se envía.

> [!WARNING]
> Debe ejecutar el ejemplo como administrador.

Puede descargar la solución completa de Visual Studio del [ejemplo de encadenador para .NET Framework 4.5](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba) en la galería de ejemplos de MSDN.

En las secciones siguientes se describen los archivos importantes de este ejemplo: MMIOChainer.h, ChainingdotNet4.cpp e IProgressObserver.h.

#### <a name="mmiochainerh"></a>MMIOChainer.h

- El archivo MMIOChainer.h (vea el [código completo](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=663039622)) contiene la definición de la estructura de datos y la clase base de la que debería derivarse la clase del encadenador. .NET Framework 4.5 amplía la estructura de datos MMIO para controlar los datos que necesita su instalador. Los cambios en la estructura MMIO son compatible con versiones anteriores, por lo que un encadenador de .NET Framework 4 puede trabajar con el programa de instalación de .NET Framework 4.5 sin necesidad de volver a compilar. Sin embargo, este escenario no es compatible con la característica para reducir los reinicios del sistema.

    Un campo de versión proporciona un medio de identificar las revisiones para la estructura y el formato de mensajes. El programa de instalación de .NET Framework determina la versión de la interfaz del encadenador llamando a la función `VirtualQuery` para averiguar el tamaño de la asignación del archivo. Si el tamaño es lo suficientemente grande para acomodar el campo de versión, el programa de instalación de .NET Framework utiliza el valor especificado. Si la asignación del archivo es demasiado pequeña para contener un campo de versión, que es lo que sucede con .NET Framework 4, el proceso de instalación asume que es la versión 0 (4). Si el encadenador no admite la versión del mensaje que el programa de instalación de .NET Framework desea enviar, este asume que la respuesta es ignorar.

    La estructura de datos MMIO se define como sigue:

    ```cpp
    // MMIO data structure for interprocess communication
        struct MmioDataStructure
        {
            bool m_downloadFinished;               // Is download complete?
            bool m_installFinished;                // Is installation complete?
            bool m_downloadAbort;                  // Set to cause downloader to abort.
            bool m_installAbort;                   // Set to cause installer to abort.
            HRESULT m_hrDownloadFinished;          // Resulting HRESULT for download.
            HRESULT m_hrInstallFinished;           // Resulting HRESULT for installation.
            HRESULT m_hrInternalError;
            WCHAR m_szCurrentItemStep[MAX_PATH];
            unsigned char m_downloadSoFar;         // Download progress 0-255 (0-100% done).
            unsigned char m_installSoFar;          // Installation progress 0-255 (0-100% done).
            WCHAR m_szEventName[MAX_PATH];         // Event that chainer creates and chainee opens to sync communications.

            BYTE m_version;                        // Version of the data structure, set by chainer:
                                                   // 0x0: .NET Framework 4
                                                   // 0x1: .NET Framework 4.5

            DWORD m_messageCode;                   // Current message sent by the chainee; 0 if no message is active.
            DWORD m_messageResponse;               // Chainer's response to current message; 0 if not yet handled.
            DWORD m_messageDataLength;             // Length of the m_messageData field, in bytes.
            BYTE m_messageData[1];                 // Variable-length buffer; content depends on m_messageCode.
        };
    ```

- La estructura de datos `MmioDataStructure` no debe utilizarse directamente; use la clase `MmioChainer` en su lugar para implementar el encadenador. Realice una derivación a partir de la clase `MmioChainer` para encadenar el paquete redistribuible de .NET Framework 4.5.

#### <a name="iprogressobserverh"></a>IProgressObserver.h

- El archivo IProgressObserver.h implementa un observador de progreso ([vea el código completo](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=1263700592)). Este observador recibe notificaciones del progreso de descarga e instalación (se especifica como un `char` sin firmar, 0-255, que indica 1-100 % completado). El observador también recibe una notificación cuando el objeto encadenado envía un mensaje y debe enviar una respuesta.

    ```cpp
        class IProgressObserver
        {
        public:
            virtual void OnProgress(unsigned char) = 0; // 0 - 255:  255 == 100%
            virtual void Finished(HRESULT) = 0;         // Called when operation is complete
            virtual DWORD Send(DWORD dwMessage, LPVOID pData, DWORD dwDataLength) = 0; // Called when a message is sent
        };
    ```

#### <a name="chainingdotnet45cpp"></a>ChainingdotNet4.5.cpp

- El archivo [ChainingdotNet4.5.cpp](https://code.msdn.microsoft.com/NET-Framework-45-Developer-e416a0ba/sourcecode?fileId=47345&pathId=1757268882) implementa la clase `Server`, que deriva de la clase `MmioChainer` e invalida los métodos adecuados para mostrar la información de progreso. El MmioChainer crea una sección con el nombre de la sección especificada e inicializa al encadenador con el nombre de evento especificado. El nombre del evento se guarda en la estructura de datos asignada. Los nombres de sección y de evento deben ser únicos. La clase `Server` del código siguiente inicia el programa de instalación especificado, supervisa su progreso y devuelve un código de salida.

    ```cpp
    class Server : public ChainerSample::MmioChainer, public ChainerSample::IProgressObserver
    {
    public:
        …………….
        Server():ChainerSample::MmioChainer(L"TheSectionName", L"TheEventName") //customize for your event names
        {}
    ```

    La instalación se inicia en el método Main.

    ```cpp
    // Main entry point for program
    int __cdecl main(int argc, _In_count_(argc) char **_argv)
    {
        int result = 0;
        CString args;
        if (argc > 1)
        {
            args = CString(_argv[1]);
        }

        if (IsNetFx4Present(NETFX45_RC_REVISION))
        {
            printf(".NET Framework 4.5 is already installed");
        }
        else
        {
            result = Server().Launch(args);
        }

        return result;
    }
    ```

- Antes de iniciar la instalación, el encadenador comprueba si .NET Framework 4.5 ya está instalado mediante una llamada a `IsNetFx4Present`:

    ```cpp
    ///  Checks for presence of the .NET Framework 4.
    ///    A value of 0 for dwMinimumRelease indicates a check for the .NET Framework 4 full
    ///    Any other value indicates a check for a specific compatible release of the .NET Framework 4.
    #define NETFX40_FULL_REVISION 0
    // TODO: Replace with released revision number
    #define NETFX45_RC_REVISION MAKELONG(50309, 5)   // .NET Framework 4.5
    bool IsNetFx4Present(DWORD dwMinimumRelease)
    {
        DWORD dwError = ERROR_SUCCESS;
        HKEY hKey = NULL;
        DWORD dwData = 0;
        DWORD dwType = 0;
        DWORD dwSize = sizeof(dwData);

        dwError = ::RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full", 0, KEY_READ, &hKey);
        if (ERROR_SUCCESS == dwError)
        {
            dwError = ::RegQueryValueExW(hKey, L"Release", 0, &dwType, (LPBYTE)&dwData, &dwSize);

            if ((ERROR_SUCCESS == dwError) && (REG_DWORD != dwType))
            {
                dwError = ERROR_INVALID_DATA;
            }
            else if (ERROR_FILE_NOT_FOUND == dwError)
            {
                // Release value was not found, let's check for 4.0.
                dwError = ::RegQueryValueExW(hKey, L"Install", 0, &dwType, (LPBYTE)&dwData, &dwSize);

                // Install = (REG_DWORD)1;
                if ((ERROR_SUCCESS == dwError) && (REG_DWORD == dwType) && (dwData == 1))
                {
                    // treat 4.0 as Release = 0
                    dwData = 0;
                }
                else
                {
                    dwError = ERROR_INVALID_DATA;
                }
            }
        }

        if (hKey != NULL)
        {
            ::RegCloseKey(hKey);
        }

        return ((ERROR_SUCCESS == dwError) && (dwData >= dwMinimumRelease));
    }
    ```

- Puede cambiar la ruta de acceso del archivo ejecutable (Setup.exe en el ejemplo) en el método `Launch` para que apunte a su ubicación correcta o personalizar el código para determinarla. La clase base `MmioChainer` proporciona un método `Run()` de bloqueo al que llama la clase derivada.

    ```cpp
    bool Launch(const CString& args)
    {
    CString cmdline = L"dotNetFx45_Full_x86_x64.exe -pipe TheSectionName " + args; // Customize with name and location of setup .exe that you want to run
    STARTUPINFO si = {0};
    si.cb = sizeof(si);
    PROCESS_INFORMATION pi = {0};

    // Launch the Setup.exe that installs the .NET Framework 4.5
    BOOL bLaunchedSetup = ::CreateProcess(NULL,
     cmdline.GetBuffer(),
     NULL, NULL, FALSE, 0, NULL, NULL,
     &si,
     &pi);

    // If successful
    if (bLaunchedSetup != 0)
    {
    IProgressObserver& observer = dynamic_cast<IProgressObserver&>(*this);
    Run(pi.hProcess, observer);

    ……………………..
    return (bLaunchedSetup != 0);
    }
    ```

- El método `Send` intercepta y procesa los mensajes. En esta versión de .NET Framework, el único mensaje admitido es el mensaje para cerrar la aplicación.

    ```cpp
            // SendMessage
            //
            // Send a message and wait for the response.
            // dwMessage: Message to send
            // pData: The buffer to copy the data to
            // dwDataLength: Initially a pointer to the size of pBuffer. Upon successful call, the number of bytes copied to pBuffer.
            //--------------------------------------------------------------
        virtual DWORD Send(DWORD dwMessage, LPVOID pData, DWORD dwDataLength)
        {
            DWORD dwResult = 0;
            printf("received message: %d\n", dwMessage);
            // Handle message
            switch (dwMessage)
            {
            case MMIO_CLOSE_APPS:
                {
                    printf("    applications are holding files in use:\n");
                    IronMan::MmioCloseApplications* applications = reinterpret_cast<IronMan::MmioCloseApplications*>(pData);
                    for(DWORD i = 0; i < applications->m_dwApplicationsSize; i++)
                    {
                        printf("      %ls (%d)\n", applications->m_applications[i].m_szName, applications->m_applications[i].m_dwPid);
                    }

                    printf("    should appliations be closed? (Y)es, (N)o, (R)efresh : ");
                    while (dwResult == 0)
                    {
                        switch (toupper(getwchar()))
                        {
                        case 'Y':
                            dwResult = IDYES;  // Close apps
                            break;
                        case 'N':
                            dwResult = IDNO;
                            break;
                        case 'R':
                            dwResult = IDRETRY;
                            break;
                        }
                    }
                    printf("\n");
                    break;
                }
            default:
                break;
            }
            printf("  response: %d\n  ", dwResult);
            return dwResult;
        }
    };
    ```

- Los datos de progreso son un `char` sin signo y estarán comprendidos entre 0 (0 %) y 255 (100 %).

    ```cpp
    private: // IProgressObserver
        virtual void OnProgress(unsigned char ubProgressSoFar)
        {…………
       }
    ```

- HRESULT se pasa al método `Finished`.

    ```cpp
    virtual void Finished(HRESULT hr)
    {
    // This HRESULT is communicated over MMIO and may be different than process
    // Exit code of the Chainee Setup.exe itself
    printf("\r\nFinished HRESULT: 0x%08X\r\n", hr);
    }
    ```

    > [!IMPORTANT]
    > El programa redistribuible de .NET Framework 4.5 normalmente escribe muchos mensajes de progreso y un solo mensaje que indica la finalización del proceso (en el lado del encadenador). También realiza lecturas asincrónicas en busca de registros `Abort`. Si recibe un registro `Abort`, se cancela la instalación y se escribe un registro de finalización usando E_ABORT como datos después que la instalación se ha anulado y las operaciones de instalación se han revertido.

Un servidor normal crea un nombre de archivo MMIO aleatorio, crea el archivo (tal y como se muestra en el ejemplo de código anterior, en `Server::CreateSection`) e inicia el programa redistribuible usando el método `CreateProcess` y pasando el nombre de la canalización con la opción `-pipe someFileSectionName`. El servidor debe implementar los métodos `OnProgress`, `Send` y `Finished` con código específico de la interfaz de usuario de la aplicación.

## <a name="see-also"></a>Vea también

- [Guía de implementación para desarrolladores](deployment-guide-for-developers.md)
- [Implementación](index.md)
