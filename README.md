#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
 
int main (int argc, char * argv[])
{

int s_led (FILE * led, int wert)
{

	fprintf(led,"%d",wert);
	fflush(led);
}

FILE * export;
        export = fopen("/sys/class/gpio/export", "w");
        fprintf(export, "0");
        fflush (export);
        fclose(export);
        
        
FILE * direction;

        direction = fopen("/sys/class/gpio/gpio0/direction","w");
        fprintf(direction, "out");
        fclose (direction);
FILE * value0;
        value0 =fopen("/sys/class/gpio/gpio0/value","w");
        fflush(value0);
        

	usleep (time);
	s_led (value1, 1);


	
	FILE * fp;
	int fd;
	
	fp=fopen("/sys/class/gpio/export","w");
	fprintf(fp,"9\n");
	fclose(fp);
	
	fp=fopen("/sys/class/gpio/gpio9/direction","w");
	fprintf(fp,"in");
	fclose(fp);
	
	fp=fopen("/sys/class/gpio/gpio9/value","r");
	
	int rc;
	char buf[3];
	fd=fileno(fp);
	while (1){
		usleep(50000);
		lseek (fd, 0L, SEEK_SET);
		read(fd, buf,3);
	if (buf[0] == '1'){
		printf ("An \r");
	}
	else{
		printf("Aus\r");
	}	
	
		fflush(stdout);
	}

	
}
