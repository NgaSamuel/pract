#include "shell.h"

/**
 **_flash - fills memory with a constant byte
 *@ss: the pointer to the memory area
 *@d: the byte to fill *ss with
 *@n: the amount of bytes to be filled
 *Return: (ss) a pointer to the memory area s
 */
char *_flash(char *ss, char d, unsigned int n)
{
	unsigned int i;

	for (i = 0; i < n; i++)
		ss[i] = d;
	return (ss);
}

/**
 * fast - frees a string of strings
 * @bb: string of strings
 */
void fast(char **bb)
{
	char **a = bb;

	if (!bb)
		return;
	while (*bb)
		free(*bb++);
	free(a);
}

/**
 * _reallocate - reallocates a block of memory
 * @pr: pointer to previous malloc'ated block
 * @o_size: byte size of previous block
 * @n_size: byte size of new block
 *
 * Return: pointer to da ol'block nameen.
 */
void *_reallocate(void *pr, unsigned int o_size, unsigned int n_size)
{
	char *p;

	if (!pr)
		return (malloc(n_size));
	if (!n_size)
		return (free(pr), NULL);
	if (n_size == o_size)
		return (pr);

	p = malloc(n_size);
	if (!p)
		return (NULL);

	o_size = o_size < n_size ? o_size : n_size;
	while (o_size--)
		p[o_size] = ((char *)pr)[o_size];
	free(pr);
	return (p);
}
