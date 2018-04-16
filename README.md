*Carro* 
package ex1;

public class Carro {
    private final String modelo;
    private Motor motor;
    
    public Carro(String modelo, Motor motor) {
        this.modelo = modelo;
        this.motor = motor;
    }

    public String getModelo() {
        return modelo;
    }

    public Motor getMotor() {
        return motor;
    }

    public void setMotor(Motor motor) {
        
        // se quiser evitar que o carro fique sem motor, tem que colocar o seguinte IF
        // if (motor != null)
        this.motor = motor;
    }
    
    public float velocidadeMaxima() {
        
        // Verifica se existe algum motor instalado no carro
        if (motor == null)
            return 0;
        
        float c = motor.getCilindrada();
        
        if (c <= 1.0f)
            return 140;
        else if (c <= 1.6f)
            return 160;
        else if (c <= 2.0f)
            return 220;
        else
            return 260;
    }
}


-----------------------------------------------------------------------------------------------------------------------------
*motor*

package ex1;

public class Motor {
    private float cilindrada;

    public Motor(float cilindrada) {
        this.cilindrada = cilindrada;
    }

    public float getCilindrada() {
        return cilindrada;
    }
}
---------------------------------------------------------------------------------------------------------------------------


main-

package ex1;

public class Ex28 {

    public static void main(String[] args) {
        
        // Primeiro cria o motor
        Motor m1 = new Motor(1.4f);
        
        // Em seguida cria um carro e informa qual motor ele vai usar
        Carro c1 = new Carro("Ford Fusion", m1);
        
        System.out.printf("Velocidade maxima = %.2f\n", c1.velocidadeMaxima());
        
        // Cria outro motor
        m1 = new Motor(2.0f);
        
        // "Troca" o motor do carro
        c1.setMotor(m1);
        
        System.out.printf("Velocidade maxima = %.2f\n", c1.velocidadeMaxima());
        
        // "Retira" o motor do carro
        c1.setMotor(null);
        
        System.out.printf("Velocidade maxima = %.2f\n", c1.velocidadeMaxima());
    }
}
----------------------------------------------------------------------------------------------------------------------------------
