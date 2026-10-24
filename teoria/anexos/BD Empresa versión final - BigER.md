
```code
erdiagram EmpresaFinal
notation=crowsfoot
```

---
### Entidades
####  Entidad Empleado
```code
entity Empleado {
dni key
nombre
apellido_1
apellido_2
fecha_nacimiento
direccion
sexo
sueldo
}
```
#### Entidad Departamento
```code
entity Departamento {
numero_departamento key
nombre unique
}
```
#### Entidad Proyecto
```code
entity Proyecto {
numero_proyecto key
nombre unique
ubicacion
}
```

---
### Relaciones
#### Relación trabaja_para
```code
relationship trabaja_para {
Empleado[1..N] -> Departamento[1..1]
}
```
#### Relación dirige
```code
relationship dirige {
Empleado[1..1] -> Departamento[0..1]
fecha_ingreso_director
}
```
#### Relación trabaja_en
```code
relationship trabaja_en {
Empleado[1..N] -> Proyecto[0..N]
horas
}
```
#### Relación controla
```code
relationship controla {
Proyecto[0..N] -> Departamento[1..1]
}
```
#### Relación supervisa
```code
relationship supervisa {
Empleado[0..1 | "Supervisor" ] -> Empleado[0..N | "Supervisado"]
}
```

---
### Entidades y relaciones débiles

#### Entidad débil Familiar
```code
weak entity Familiar {
nombre partial-key
sexo
fecha_nacimiento
relacion
}
```
#### Relación débil familiar_de 
```code
weak relationship familiar_de {
Familiar[0..N] -> Empleado[1..1]
}
```
#### Entidad débil Ubicacion_Departamento
```code
weak entity Ubicacion_Departamento {
nombre partial-key
}
```
#### Relación débil ubicado_en
```code
weak relationship ubicado_en {
Departamento[1..1] -> Ubicacion_Departamento[1..N]
}
```

---
### Diagrama resultante en notación crow's foot

![](../../imgs/BD%20-%20BigER%20Empresa%20version%20final%20correcta.png)
