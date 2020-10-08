# Demo: Caso de uso Cloud Pak for Integración

A partir de la guía expuesta en el playbook, este documento busca ilustrar los pasos realizados con una descripción detallada sobre los errores y complicaciones a lo largo del proceso de creación de la demostración.

Para la ejecución de los comandos se utilizó el IBM Cloud Shell con acceso al cluster donde está instalado el Cloud Pak for Integration.

# Instalación de Event Streams

## Preparando la instalación

1. Se pudo ejecutar sin ningún problema

2. En el paso 2, no se especifica la forma en la que se pueden ejecutar los comandos en los nodos del cluster. En el dashboard de Openshift tampoco se encontró la forma de acceder a un terminal que esté direccionado al nodo.

3. No hubo problema al ejecutar los comandos.

## Comenzando la instalación

Antes de iniciar se nos pide especificar un Group ID para el Sistema de Archivos (File System Group ID) con un valor de 1000. Sin embargo, no es claro la forma en la que se configura este valor.

Se colocaron los valores de acuerdo a la guía del Playbook, en la siguiente tabla están los valores usados para la instalación.

| Configuración | Valor usado |
|---|---|
| Helm Release Name | es-1 |
| Target Namespace | eventstreams |
| Cluster | local-cluster |
| License Agreement | :check: |
| Namespace where the Platform Navigator is installed  | integration |

Expandir la sección **Quick Start**

| Configuración | Valor usado |
|---|---|
| Certificate Secret Name | eventstreamssecret |
| Image Pull Secret | ibm-entitlement-key* |
| External Access Settings | External hostname/IP Address** |

* La llave debe ser creada con anterioridad, se puede consultar el nombre de la llave usando el comando `oc get secrets`
** icp-proxy.cloudpakforintegration-36dc22295c06f3c7441900a793344103-0000.us-south.containers.appdomain.cloud

Expandir la sección **All Parameters**

| Configuración | Valor usado |
|---|---|
| File System Group ID | 1000 |
| Persistent Storage | ibmc-block-gold |

## Validar la instalación

Utilizando el comando `oc get pods` teniendo seleccionado el project evenstreams 