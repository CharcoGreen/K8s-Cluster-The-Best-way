# Kubernetes La mejor forma de organizar los manifestos

Cuando creamos un clúster con varios entornos, nos encontramos con el problema de que cada uno de ellos necesita diferentes manifestos en ficheros yaml.
Esto puedo generar una cantidad de inconvenientes.

Por ejemplo, un cluster o varios cluster con entornos diferentes, integración, producción o preproducción.  
Cada uno de estos entornos necesita diferentes definiciones de en los yaml, piensa en un componente de infraestrucctura, por ejemplo, elasticsearch con todos sus componentes, necesitarías una carpeta por cada componente con los yaml diferentes para cada una de las infraestructuras. También se puede ocurrir crear scripts con sustituciones de variables de entorno y ficheros de ejecución staticos para cada uno de los stacks, esto puede ser una buena idea, pero piensa que si cambias algo de estos ficheros comunes tendrás un impacto en el resto de componentes.

Por este motivo busco la mejor opción para alivianar este trabajo y algunas opciones que me he encontrado son:

- Shell Bash scripts  (No lo recomiendo)
- kustomize.          
- ansible
- Helm charts

El objetivo de este repo es probar cada uno de ellos y ver cuál es la mejor.

## Sugerencias

Write your own helm charts and use flux to back your clusters with a git repo, have a folder per environment and use helm-operator in conjunction with flux to      deploy releases of your own charts

  https://github.com/fluxcd/flux  
  https://helm.sh/  
  https://docs.fluxcd.io/projects/helm-operator/en/stable/  
  https://docs.fluxcd.io/  
