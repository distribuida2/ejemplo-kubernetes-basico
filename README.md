# Kubernetes básico

Pequeño ejemplo para ver durante la primer clase de Kubernetes

## Algunas instrucciones básicas

Para instanciar los objetos, se debe llamar al subcomando `apply` de kubectl.

Por ejemplo

`kubectl apply -f busybox_pod.yaml`

## busybox_pod.yaml

El objeto definido es un **pod**, la mínima unidad instanciable de Kubernetes. Cada pod puede tener dentro uno o más contenedores. En este caso es solo un contenedor que tiene el binario de Busybox.

Para instanciar el pod

`kubectl apply -f busybox_pod.yaml`

Y para meterse dentro del contenedor

`kubectl exec -ti busybox1 -- sh`

## deployment_saludador.yaml

Este archivo contiene un objeto de tipo **deployment**. Al aplicarlo, lo que hace es crear un deployment de un replica set con dos pods del viejo y conocido Saludador (el primer ejempo que vimos en la materia cuando vimos Docker).

`kubectl apply -f deployment_saludador.yaml`

## svc_saludador_lb.yaml

Este es el servicio de tipo **NodePort** que nos da acceso desde el exterior al servicio y al deployment que definimos anteriormente.

`kubectl apply -f svc_saludador_lb.yaml`
