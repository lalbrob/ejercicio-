
Exercicios de lóxica de programación
Israel
•
12:32 PM
A partir dos exercicios que están no arquivo subido. 
Crea un repositorio en github onde deberás subir as solucións propostas.

Exercicios_Loxica.txt
Text
Your work
Assigned
Private comments
Class comments
/**
 *  =======================
 *  ··· P E R S O N A S ···
 *  =======================
 */
const persons = [
    {
      name: 'Pedro',
      age: 35,
      country: 'ES',
      infected: true,
      pet: 'Troski'
    },
    {
      name: 'Elisabeth',
      age: 14,
      country: 'UK',
      infected: true,
      pet: 'Firulais'
    },
    {
      name: 'Pablo',
      age: 25,
      country: 'ES',
      infected: false,
      pet: 'Berritxu'
    },
    {
      name: 'Angela',
      age: 18,
      country: 'DE',
      infected: false,
      pet: 'Noodle'
    },
    {
      name: 'Boris',
      age: 50,
      country: 'UK',
      infected: true,
      pet: 'Leon'
    },
    {
      name: 'Donald',
      age: 69,
      country: 'US',
      infected: false,
      pet: 'Pence'
    },
    {
      name: 'Pepito',
      age: 36,
      country: 'ES',
      infected: false,
      pet: 'Carbón'
    }
  ];

  /**
   *  =======================
   *  ··· M A S C O T A S ···
   *  =======================
   */
  const pets = [
    {
      name: 'Troski',
      type: 'perro'
    },
    {
      name: 'Firulais',
      type: 'perro'
    },
    {
      name: 'Berritxu',
      type: 'loro'
    },
    {
      name: 'Noodle',
      type: 'araña'
    },
    {
      name: 'Leon',
      type: 'gato'
    },
    {
      name: 'Pence',
      type: 'perro'
    },
    {
      name: 'Carbón',
      type: 'gato'
    }
  ];

  /**
   *  =======================
   *  ··· A N I M A L E S ···
   *  =======================
   */
  const animals = [
    {
      kind: 'perro',
      legs: 4
    },
    {
      kind: 'araña',
      legs: 8
    },
    {
      kind: 'gato',
      legs: 4
    },
    {
      kind: 'loro',
      legs: 2
    },
    {
      kind: 'gallina',
      legs: 2
    }
  ];

  /**
   *  ===================
   *  ··· P A Í S E S ···
   *  ===================
   */
  const countries = [
    {
      code: 'CN',
      name: 'China',
      population: 1439,
      infected: 81999
    },
    {
      code: 'US',
      name: 'Estados Unidos',
      population: 331,
      infected: 112468
    },
    {
      code: 'DE',
      name: 'Alemania',
      population: 83,
      infected: 56202
    },
    {
      code: 'ES',
      name: 'España',
      population: 46,
      infected: 72248
    },
    {
      code: 'UK',
      name: 'Reino Unido',
      population: 67,
      infected: 17301
    }
  ];

/*   module.exports = {
      persons,
      countries,
      animals,
      pets
  } */

  /**


EJERCICIO 1: Número total de infectados del array de personas
const infectadosPersonas = persons.filter(p => p.infected).length;
console.log('Infectados (personas):', infectadosPersonas);

EJERCICIO 2: Número total de sanos
const sanos = persons.filter(p => !p.infected).length;
console.log('Sanos:', sanos);

EJERCICIO 3: Total de infectados por países
const totalInfectadosPaises = countries.reduce((acc, c) => acc + c.infected, 0);
console.log('Infectados (paises):', totalInfectadosPaises);

EJERCICIO 4: País con más infectados
const paisMasInfectado = countries.reduce((max, c) => c.infected > magit add README.md
git commit -m "Actualizar README.md"
git pushx.infected ? c : max);
console.log('País con más infectados:', paisMasInfectado.name);

EJERCICIO 5: Array con el nombre de todas las mascotas
const nombresMascotas = pets.map(p => p.name);
console.log('Nombres de mascotas:', nombresMascotas);

EJERCICIO 6: Array con las personas infectadas
const personasInfectadas = persons.filter(p => p.infected);
console.log('Personas infectadas:', personasInfectadas);

EJERCICIO 7: Array de españoles con perro
const espanolesConPerro = persons.filter(p => 
  p.country === 'ES' && 
  pets.find(m => m.name === p.pet && m.type === 'perro')
);
console.log('Españoles con perro:', espanolesConPerro);

EJERCICIO 8: Personas con objeto mascota incluido
const personasConMascota = persons.map(p => ({
  ...p,
  petData: pets.find(m => m.name === p.pet)
}));
console.log('Personas con datos de mascota:', personasConMascota);

EJERCICIO 9: Animal que más personas tienen como mascota
const conteoMascotas = {};
persons.forEach(p => {
  const tipo = pets.find(m => m.name === p.pet)?.type;
  if (tipo) conteoMascotas[tipo] = (conteoMascotas[tipo] || 0) + 1;
});
const animalFavorito = Object.entries(conteoMascotas).reduce((max, curr) => curr[1] > max[1] ? curr : max);
console.log('Animal más común como mascota:', animalFavorito[0]);

EJERCICIO 10: Número total de patas de mascotas
const totalPatas = persons.reduce((acc, p) => {
  const tipoMascota = pets.find(m => m.name === p.pet)?.type;
  const patas = animals.find(a => a.kind === tipoMascota)?.legs || 0;
  return acc + patas;
}, 0);
console.log('Total de patas de las mascotas de las personas:', totalPatas);

EJERCICIO 11: Personas con animales de 4 patas
const personasCon4Patas = persons.filter(p => {
  const tipo = pets.find(m => m.name === p.pet)?.type;
  const patas = animals.find(a => a.kind === tipo)?.legs;
  return patas === 4;
});
console.log('Personas con mascotas de 4 patas:', personasCon4Patas);

EJERCICIO 12: Personas no infectadas de 'España'
const personasNoInfectadasEsp = persons.filter(p => p.country === 'ES' && !p.infected);
console.log('Personas no infectadas de España:', personasNoInfectadasEsp);

 EJERCICIO 13: Países con personas que tienen loros 
const paisesConLoros = persons
  .filter(p => pets.find(m => m.name === p.pet)?.type === 'loro')

  .map(p => countries.find(c => c.code === p.country)?.name)
  .filter((name, i, arr) => name && arr.indexOf(name) === i);
console.log('Países con personas con loros:', paisesConLoros);

// EJERCICIO 14: Infectados en países con mascotas de 8 patas
const tipos8Patas = animals.filter(a => a.legs === 8).map(a => a.kind);
const paisesCon8Patas = persons
  .filter(p => tipos8Patas.includes(pets.find(m => m.name === p.pet)?.type))
  .map(p => p.country);

const codigosUnicos = [...new Set(paisesCon8Patas)];
const infectados8Patas = countries
  .filter(c => codigosUnicos.includes(c.code))
  .reduce((acc, c) => acc + c.infected, 0);
console.log('Infectados en países con mascotas de 8 patas:', infectados8Patas);
