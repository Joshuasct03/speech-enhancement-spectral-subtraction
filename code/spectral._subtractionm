[noisy_signal, fs] = audioread('noisy_speech.wav');
frame_size = 256;
overlap = frame_size / 2;
window =hamming(frame_size);
num_frames = floor((length(noisy_signal)- overlap) /
(frame_size- overlap));
enhanced_signal = zeros(size(noisy_signal));
noise_estimate = zeros(frame_size, 1);
for k = 1:num_frames
start_index = (k- 1) * (frame_size- overlap) + 1;
end_index = start_index + frame_size- 1;
frame = noisy_signal(start_index:end_index) .* window;
frame_fft = fft(frame);
magnitude = abs(frame_fft);
phase = angle(frame_fft);
if k == 1
noise_estimate = magnitude;
else
noise_estimate = 0.9 * noise_estimate + 0.1 * magnitude;
end
alpha = 2;
enhanced_magnitude = max(magnitude- alpha *
noise_estimate, 0);
enhanced_frame_fft = enhanced_magnitude .* exp(1i *
phase);
enhanced_frame = real(ifft(enhanced_frame_fft));
enhanced_signal(start_index:end_index) =
enhanced_signal(start_index:end_index) + enhanced_frame .*
window;
end
enhanced_signal = enhanced_signal / max(abs(enhanced_signal));
audiowrite('enhanced_speech.wav', enhanced_signal, fs);
disp('Playing noisy speech...');
sound(noisy_signal, fs);
pause(length(noisy_signal)/fs + 1);
disp('Playing enhanced speech...');
sound(enhanced_signal, fs);
pause(length(enhanced_signal)/fs + 1);
figure;
subplot(2, 1, 1);
plot(noisy_signal);
title('Noisy Speech Signal');
xlabel('Samples');
ylabel('Amplitude');
subplot(2, 1, 2);
plot(enhanced_signal);
title('Enhanced Speech Signal');
xlabel('Samples');
ylabel('Amplitude');
