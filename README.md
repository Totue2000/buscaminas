#include <SFML/Graphics.hpp>
#include <iostream>



int main()
{
	srand(time(0));

	sf::RenderWindow windows(sf::VideoMode(400, 400), "Minesweeper!");

	int w = 32;
	int grid[12][12];
	int sgrid[12][12];

	sf::Texture texture;
	if (!texture.loadFromFile("buscaminas.png"))
		return EXIT_FAILURE;


	for (int i=1;i<=10;i++)
		for (int j = 1;j <= 10;j++)
		{
			sgrid[i][j] = 10;
			if (rand() % 5 == 0) grid[i][j] = 9;
			else grid[i][j] = 0;
		}
		for (int i=1;i<=10;i++)
			for (int i = 1;i <= 10;i++)
			{
				int n = 0;
				if (grid[i][j] == 9) continue;
				if (grid[i + 1][j] == 9) n++;
				if (grid[i][j + 1] == 9) n++;
				if (grid[i - 1][j] == 9) n++;
				if (grid[i][j - 1] == 9) n++;
				if (grid[i + 1][j + 1] == 9) n++;
				if (grid[i - 1][j - 1] == 9) n++;
				if (grid[i - 1][j + 1] == 9) n++;
				if (grid[i + 1][j - 1] == 9) n++;
				grid[i][j] = n;
			}
	while (windows.isOpen())
	{
		_VECTOR_ = mouse::getPosition();
		*****


		sf::Event event;
		while (windows.pollEvent(event))
		{
			if (e.type == event::closed)
				windows.close();

				if (e.type == event::MouseBottonPressed)
					if (e.key.code == SFML_MOUSE_HPP::Left)sgrid[x][y] = grid[x][y];
					else if (e.key.code == SFML_MOUSE_HPP::Right)sgrid[x][y] = 11;

		}
		windows.clear(SFML_COLOR_HPP);
		for(int i=1;i<=10;i++)
		for (int j = 1;j <= 10;j++)
		{
			if (sgrid[x][y] == 9) sgrid[i][j] = grid[i][j];
			sgrid[i][j] = grid[i][j];
		


		 windows.draw;

		}
		return EXIT_SUCCESS;

	}




}
