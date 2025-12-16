import java.util.ArrayList;
import java.util.Scanner;

public static class Main {

    public static void addTarefas(Scanner lt, ArrayList<Tarefas> lista){
        boolean cont = true;
        String res;
        while(cont){
            System.out.println("Digite a tarefa: ");
            Tarefas t1 = new Tarefas(lt.nextLine());
            lista.add(t1);

            System.out.println("Deseja continuar? (s/n)");
            res = lt.nextLine();

            switch (res) {
                case "s" -> cont = true;
                case "n" -> cont = false;
                default -> System.out.println("Invalido!, digite somente (s/n)");
            }
        }
    }
    public static void modTarefas (Scanner lt, ArrayList<Tarefas> lista){
        String res;
        System.out.println("Qual e o numero da tarefa voce deseja modificar?");
        int num = lt.nextInt();
        lt.nextLine();
        int ind = num - 1;
        if (ind >= 0 && ind < lista.size()) {
            System.out.println("A tarefa " + lista.get(ind).getNome() + " foi concluida?");
            res = lt.nextLine();
            switch (res) {
                case "sim" -> lista.get(ind).setEstado(true);
                case "nao" -> lista.get(ind).setEstado(false);
                default -> System.out.println("Invalido!, digite somente (sim ou nao)");
            }
        } else {
            System.out.println(" Erro! Número de tarefa inválido.");
        }
    }
    public static void delTarefas (Scanner lt, ArrayList<Tarefas> lista){
        String res;
        System.out.println("Qual e o numero da tarefa voce deseja deletar?");
        int num = lt.nextInt();
        lt.nextLine();
        int ind = num - 1;
        if (ind >= 0 && ind < lista.size()) {
            System.out.println("Tem certeza que quer remover a tarefa: " + lista.get(ind).getNome());
            res = lt.nextLine();
            if (res.equals("sim")) {
                lista.remove(ind);
            } else {
                System.out.println("Invalido!, digite somente (sim ou nao)");
            }
    } else {
        System.out.println("Erro! Número de tarefa inválido.");
    }}
    }
    public static void exbTarefas (ArrayList<Tarefas> lista){
        System.out.println("Essas sao suas tarefas:");
        String estadoText;
        for(int i = 0; i < lista.size(); i++){
            if(!lista.get(i).getEstado()){
                estadoText = "Pendente";
            }else {
                estadoText = "Concluida";
            }
            System.out.println((i + 1) + ". " + lista.get(i).getNome() + " - " + estadoText);
        }
    }

    void main() {
        Scanner lt = new Scanner(System.in);
        ArrayList<Tarefas> lista = new ArrayList<>();
        int opcao;

        do {
            System.out.println("\n=== MENU ===");
            System.out.println("1. Adicionar Tarefa");
            System.out.println("2. Exibir Tarefas");
            System.out.println("3. Modificar Tarefa");
            System.out.println("4. Deletar Tarefa");
            System.out.println("5. Sair");
            System.out.print("Escolha uma opção: ");

            opcao = lt.nextInt();
            lt.nextLine(); // Limpeza do buffer

            switch (opcao) {
                case 1:
                    Main.addTarefas(lt, lista);
                    break;
                case 2:
                    exbTarefas(lista);
                    break;
                case 3:
                    if (!lista.isEmpty()) {
                        exbTarefas(lista);
                        Main.modTarefas(lt, lista);
                    } else {
                        System.out.println("Lista vazia!");
                    }
                    break;
                case 4:
                    if (!lista.isEmpty()) {
                        exbTarefas(lista);
                        Main.delTarefas(lt, lista);
                    } else {
                        System.out.println(" Lista vazia!");
                    }
                    break;
                case 5:
                    System.out.println("Saindo... Até logo! ");
                    break;
                default:
                    System.out.println("Opção inválida! Tente novamente.");
            }

        } while (opcao != 5);
    }
