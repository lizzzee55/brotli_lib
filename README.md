# brotli_lib
Google brotli static library compiled for visual studio

Usage LizzZ


#include "brotli/decode.h"
#include "brotli/encode.h"
#pragma comment(lib,"brotli.lib")

class testBrotli {
public:
	int brotliEnc(std::string data, int type) {

		std::cout << "brotli encode\r\n";

		char *in = "aaaaaaabbbbbbbbbccccccccddddddddeeeeeeeefffffffffggggggggg";
		size_t in_size = strlen(in);

		size_t out_size = BrotliEncoderMaxCompressedSize(in_size);
		char *out = (char *)malloc(out_size);

		BrotliEncoderCompress(BROTLI_DEFAULT_QUALITY, BROTLI_DEFAULT_WINDOW, BROTLI_DEFAULT_MODE, in_size, (const uint8_t*)in, &out_size, (uint8_t*)out);


		printf("Input %d Output %d\r\n", in_size, out_size);

		//std::cout << output;
		return 1;
	}
}
