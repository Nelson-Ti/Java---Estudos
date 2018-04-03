package Aula1;

import javax.swing.JOptionPane;

public class Principal {

    //private static double Altura;
    public static void main(String[] args){
    
        String idade, nome, cpf;
      
            
      JOptionPane.showMessageDialog(null,"Informações");
      nome = JOptionPane.showInputDialog("Digite seu nome: \n");
      idade = JOptionPane.showInputDialog("Digite sua Idade: \n");
      cpf = JOptionPane.showInputDialog("Digite seu cpf: \n");
      
      
     JOptionPane.showMessageDialog(null,"Suas Informaçoes São: \n"
                 + " NOME :  " + (nome) + "\n"  
                 + " IDADE:  " + (idade) + "\n"
                 + " CPF:  " + (cpf), "\n", JOptionPane.INFORMATION_MESSAGE);
                 
    }
    }

