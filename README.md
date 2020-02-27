# el-carritode-compras
algoritmo de un carro  de compras en lenguaje c 
#include <stdio.h>
#define TAM 5
void menu();
void mostrar_articulos();
void agregar();
void eliminar();
void mostrar_carrito();


char *articulos[TAM]= {"1","2","3","4","5"};
int cantidad[TAM]= {0,0,0,0,0};
int precio[TAM]= {0,0,0,0,0};
int carrito[TAM]= {0,0,0,0,0};


int main()
{
    menu();
    return 0;
}


void menu() 
{
    int opc=0;
     do
	 {
        printf("\tCarrito\n");

        printf("\nEscoja una opcion:\n");
        printf("1)Ver articulos\n");
        printf("2)Agregar Articulo\n");
        printf("3)Eliminar articulo\n");
        printf("4)Mostrar carrito\n");
        printf("5)Salir\n");
        
        if(scanf("%d",&opc)==1)
		{
            switch(opc) 
			{
            	case 1:
                	mostrar_articulos();
                break;
                
            	case 2:
                	agregar();
                break;
            
				case 3:
                	eliminar();
                break;
            	
				case 4:
                	mostrar_carrito();
                break;        
            }
		}
		else
		{
			getchar();
		}		
    }while(opc!=5);
}


void mostrar_articulos() 
{
    int i=0;
    
    for(i ; i<TAM; i++) 
	{
        printf("%d\t%s\t%d\n",(i+1),articulos[i],cantidad[i] );
    }
}


void agregar() 
{   
    mostrar_carrito();
    int opc,cuanto;
    
    printf("\nEscoja el articulo a agregar\n");
    
    if(scanf("%d",&opc)==1) {
        printf("Cuantos articulos quieres agregar?");
        if(scanf("%d",&cuanto)==1) 
		{
            if(cuanto<=cantidad[opc-1]) 
			{
                carrito[opc-1]=carrito[opc-1]+cuánto;
                cantidad[opc-1]=cantidad[opc-1]-cuanto;
            }
            else
            {
            	printf("No hay articulos\n");
			}
        }
        else
		{
        printf("Ingresar un número\n");
        }
    }
    else
    {
    printf("Ingresar un numero\n");
    }
}


void eliminar() 
{
    mostrar_carrito();
    int opc,cuanto;
    
    printf("Escoja el articulo que quiera eliminar\n");
    
    if(scanf("%d",&opc)==1) 
	{
		if(carrito[opc-1]>0)
		{
        	printf("Cuantos articulos quieres eliminar?");
        	if(scanf("%d",&cuanto)==1) 
			{
            	if(cuanto<=cantidad[opc-1]) 
				{
                	carrito[opc-1]=carrito[opc-1]-cuanto;
                	cantidad[opc-1]=cantidad[opc-1]+cuanto;
            	}
            	else
            	{
            	printf("No hay articulos\n");
            	}
        	}
        }
        else
        {
			printf("No hay objeto\n");	
        }
        
    }
    else
    {
    printf("Ingresar un numero\n");
    }
}


void mostrar_carrito() 
{
    int pt=0;
    int i=0;
    
    printf("Producto\tCantidad\tPrecioI_unitario\tTotal\n");
    
    for(i ; i<TAM; i++) 
	{
        printf("%d%s%d%d%d\n",(i+1),articulos[i],carrito[i],precio[i],carrito[i]*precio[i]);
        pt=pt+(precio[i]*carrito[i]);
    }
    printf("Total: %d",pt);
}
